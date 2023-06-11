<script setup>
function handleStudentUpdateForm(){
  console.log("updated");
}
</script>

<template>
  <div class="shadow-md pb-6">
    <div class="bg-indigo-600 p-4">
      <h1 class="text-3xl font-bold text-center text-white">
        Edit Student-form
      </h1>
    </div>
    <form action="" class="w-full" @submit.prevent="handleStudentUpdateForm">
      <div class="flex items-center m-6">
        <div class="w-1/5">
          <label for="stuId" class="font-medium">ID:</label>
        </div>
        <div class="w-4/5">
          <input type="text" readonly disabled id="stuId" class="border=2 border-gray-200 w-full py-2 px-4" >
        </div>
      </div>

      <div class="flex items-center m-6">
        <div class="w-1/5">
          <label for="stuName" class="font-medium">Name:</label>
        </div>
        <div class="w-4/5">
          <input type="text"   id="stuName" required class="border-2 border-gray-200 w-full py-2 px-4">
        </div>
      </div>

      
      <div class="flex items-center m-6">
        <div class="w-1/5">
          <label for="stuEmail" class="font-medium">Email:</label>
        </div>
        <div class="w-4/5">
          <input type="email" id="stuEmail" required class="border-2 border-gray-200 w-full py-2 px-4">
        </div>
      </div>

     <div class="m-8 flex justify-center">
      <button type="submit" class="bg-purple-700  text-white font-medium py-2 px-2 mr-5 rounded-md hover:bg-purple-800 ">Update</button>
      <router-link :to="{name:'list'}">
        <button type="button" class="bg-emerald-700  text-white font-medium py-2 px-2 rounded-md hover ">Back to Home</button>
      </router-link>
     </div>

    </form>
  </div>
 
</template>

<style scoped>

</style>
