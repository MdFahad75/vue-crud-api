<script setup>
import { EyeIcon, PencilIcon, TrashIcon, UserPlusIcon } from '@heroicons/vue/24/solid';
import { RouterLink } from 'vue-router';
const deleteStudent = async(id)=>{
  if(!window.confirm('Are you sure want to delete?')){
    return;
  }else{
    console.log('deleted');
  }
}

</script>

<template>
  <div>
    <h1 class="text-3xl md:text-5xl font-bold text-center"> List of all students </h1>
    <RouterLink :to="{ name: 'add' }">
      <button class="text-white text-md bg-green-700 hover:bg-green-800 font-medium rounded-lg p-2 px-6 mb-2">
        <UserPlusIcon class="h-6 w-6 text-blue-500 inline" /> add new
      </button>
    </RouterLink>
  </div>
  <table id="students">
    <thead class="text-center">
      <th>NO</th>
      <th>Name</th>
      <th>Email</th>
      <th colspan="3">Action</th>
    </thead>

    <tbody>
      <tr class="text-center">
        <td>1</td>
        <td>Name 1</td>
        <td>eamil:1</td>
        <td>
          <router-link :to="{name: 'view', params: {id: 1}}">
            <EyeIcon class="h-6 w-6 text-blue-500" />
          </router-link>
          
        </td>
        <td>
          <router-link :to="{name: 'edit', params:{id: 1}}">
            <PencilIcon class="h-6 w-6 text-green-500" />
          </router-link>
         
        </td>
        <td>
          <TrashIcon class="h-6 w-6 text-red-500 cursor-pointer" @click="deleteStudent(1)" />
        </td>

      </tr>
    </tbody>
  </table>
</template>

<style scoped>
#students {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
  text-align: center;
}

#students td,
#students th {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: center;
}

#students tr:nth-child(even) {
  background-color: #f2f2f2;
}

#students tr:hover {
  background-color: #ddd;
}

#students th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: center;
  background-color: #04AA6D;
  color: white;
}</style>
