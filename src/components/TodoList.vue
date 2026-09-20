<template>
  <h1>Hello world</h1>

  <form @submit.prevent="addTask">
    <input v-model="title" type="text" placeholder="Unesite naslov zadatka" />
    <input v-model="description" type="text" placeholder="Unesite text zadatka" />
    <input v-model="dueDate" type="date" placeholder="Unesite datum zadatka" />
    <button >Snimi zadatak</button>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { TaskTypes } from '@/Types/TaskTypes'

export default defineComponent({
  name: "TodoList",
  data(): {
    title: string,
    description:string,
    dueDate:string
    tasks:TaskTypes []

  } {
    return {
      title: '',
      description:'',
      dueDate:'',
      tasks:[],

    };
  },
  methods: {
    addTask () {
       const tempTask={
         title:this.title,
         description:this.description,
         dueDate:this.dueDate
       }
      this.tasks.push(tempTask)

    }
  },
});
</script>