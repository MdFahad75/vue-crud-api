<script setup>
import { reactive } from 'vue';
import { RouterLink } from 'vue-router';
const formData = reactive({
  stuName : "",
  email : ""
});

const handleAddStudentFrom = async()=>{
  console.log("From Submited", formData);
}
</script>

<template>
  <div class="shadow-md  pb-6">
    <div class="bg-indigo-600 p-4">
      <h1 class="text-3xl font-bold text-center text-white">Add Student</h1>
    </div>
  </div>
  <form @submit.prevent="handleAddStudentFrom" class="w-full" id="addStudentForm">
    <div class="flex items-center m-6">
      <div class="w-1/5">
        <label for="stuName" class="font-medium">Name:</label>
      </div>
      <div class="w-4/5">
        <input type="text" id="stuName" v-model.trim="formData.stuName" class="border-2 border-gray-200 w-full py-2 px-4"
        placeholder="write your name" required>
      </div>
    </div>

    <div class="flex items-center m-6">
      <div class="w-1/5">
        <label for="stuEmail" class="font-medium">Email:</label>
      </div>
      <div class="w-4/5">
        <input type="email" id="stuEmail" v-model.trim="formData.email" class="border-2 border-gray-200 w-full py-2 px-4"
        placeholder="write your email address" required>
      </div>
    </div>

    <div class="m-8 flex justify-center">
      <button type="submit" class="bg-purple-700 text-white font-medium py-2 rounded-md px-6 hover:bg-purple-800 mr-6">
        Add
      </button>

      <RouterLink :to="{name: 'list'}">
        <button type="button" class="bg-emerald-700 text-white font-medium py-2 rounded-md px-6 hover:bg-emerald-800">
          Back to home
        </button>
      </RouterLink>
    </div>

  </form>
</template>

<style scoped></style>
