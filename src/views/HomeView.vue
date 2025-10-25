<template>
  <div class="w-full">
      <div class="mx-auto lg:w-7/10 w-9/10 bg-green-10">
        <div class="lg:flex lg:justify-between w-full">
          <div class="lg:w-7/10 w-full">
            <div class="grid grid-cols-2 lg:grid-cols-3 gap-2 mx-2 my-2">
              <div v-for="(d,index) in data" :key="index" @click="onMark(d.id)" :class="`border-1 rounded-lg lg:h-[140px] h-[100px] transition all-ease-in 2s hover:border-purple-500 ${d.isMark ? 'border-purple-500 bg-purple-500 text-white' : 'border-gray-200 bg-white ' }`">
                <div class="p-4">
                  {{ d.id }}
                </div>
              </div>
            </div>
          </div>
          <div class="lg:w-3/10 w-full mx-auto">
            <div class="mx-3 my-2 bg-white p-4 rounded-lg border-1 border-gray-200">
              <div class="text-[20px]">
              User Verification
            </div>
            <div class="w-full mx-auto">
              <div class="py-2">
                <label for="">
                  Game ID
                </label>
              </div>
              <div class="w-full rounded-lg border-1 border-black">
                <input type="text" class="p-2 w-full" name="" id="" placeholder="Enter ID">
              </div>
            </div>
             <div class="w-full mx-auto">
              <div class="py-2">
                <label for="">
                  Server ID
                </label>
              </div>
              <div class="w-full rounded-lg border-1 border-black">
                <input type="text" class="p-2 w-full" name="" id="" placeholder="Enter ID">
              </div>
            </div>
            <div class="w-full">
              <button class="p-4 my-4 bg-purple-400 text-white w-full rounded-lg">Check Username</button>
            </div>
            </div>
            <div class="m-4 bg-white p-4 rounded-lg border-1 border-gray-200" v-if="itemInOrder.id !== ''">
              <div class="text-[20px]">
                Payment Detail
              </div>
              <div class="my-2">
                {{ itemInOrder }}
              </div>
              <div class="w-full">
                <button class="p-4 my-4 bg-purple-400 text-white w-full rounded-lg">Check Out</button>
              </div>
            </div>
          </div>
        </div>
      </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

type Data = {
  id: string;
  name: string;
  price: number | null;
  isMark: boolean | null;
}

const itemInOrder = ref<Data>({
  id: "",
  name: "",
  price: null,
  isMark: null
})

const data = ref(
  Array.from({ length: 20 }, (_, i) => ({
    id: String(i + 1),
    name: "diamond",
    price: 100,
    isMark: false,
  }))
);


const onMark = (id: string) => {

  // reset before new selected
  data.value.forEach((item) => {
    item.isMark = false;
  });

  const itemSelected : Data | undefined = data.value.find((item) => item.id === id);
  if (!itemSelected) return;
  itemSelected.isMark = true;

  itemInOrder.value.id = itemSelected.id;
  itemInOrder.value.name = itemSelected.name;
  itemInOrder.value.price = itemSelected.price;
  itemInOrder.value.isMark = itemSelected.isMark;

}

</script>

<style scoped>

</style>
