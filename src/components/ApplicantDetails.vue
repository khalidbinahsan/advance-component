<script setup>
import {ref, computed} from 'vue'
const props = defineProps(['applicants'])
const activeIndex = ref(0)
// const person = ref(props.applicants[activeIndex.value])
const person = computed(()=>props.applicants[activeIndex.value])
const updateIndex = (index) => {
    // activeIndex.value = index
    activeIndex.value = index;
}
</script>

<template>
<div class="flex gap-10">
      <div class="w-1/4">
        <ul class="bg-slate-100 p-5 rounded">
          <li class="mb-2" v-for="(applicant, index) in applicants" :key="index">
            <a @click.prevent="activeIndex=index" class="block py-2 px-4 rounded bg-slate-200 hover:bg-slate-300 cursor-pointer" href="#">{{ applicant.name }}</a>
          </li>
        </ul>
      </div>
      <div class="bg-slate-100 p-10 rounded w-3/4">
        <h4 class="font-bold text-xl">Applicant Information</h4>
        <p>Personal details and application.</p>
        <table class="mt-5 table-auto w-full border-collapse">
          <tr>
            <td class="py-2 px-4 border-y w-1/4">Full Name</td>
            <td class="py-2 px-4 border-y w-3/4">{{ person.name }}</td>
          </tr>
          <tr>
            <td class="py-2 px-4 border-y w-1/4">Application for</td>
            <td class="py-2 px-4 border-y w-3/4">{{ person.position }}</td>
          </tr>
          <tr>
            <td class="py-2 px-4 border-y w-1/4">Email address</td>
            <td class="py-2 px-4 border-y w-3/4">{{ person.email }}</td>
          </tr>
          <tr>
            <td class="py-2 px-4 border-y w-1/4">Salary expectation</td>
            <td class="py-2 px-4 border-y w-3/4">{{ person.salary }}</td>
          </tr>
          <tr>
            <td class="py-2 px-4 border-y w-1/4">About</td>
            <td class="py-2 px-4 border-y w-3/4">{{ person.about }}</td>
          </tr>
          <tr>
            <td class="py-2 px-4 border-y w-1/4">Attachments</td>
            <td class="py-2 px-4 border-y w-3/4">
              <div class="border rounded">
                <div v-for="(attachment, index) in person.attachments" :key="index" class="flex justify-between py-2 px-3 border-y">
                  <div class="flex">
                    <img class="h-fit" src="../assets/link.png" alt="Link Icon" width="20">
                    <span class="ml-3">{{ attachment.name }}</span>
                    <span class="text-neutral-500 ml-3">{{ attachment.size }}</span>
                  </div>
                  <div><a :href="attachment.url" class="text-blue-500">Download</a></div>
                </div>
                
              </div>
            </td>
          </tr>
        </table>
      </div>
    </div>
</template>

<style scoped>

</style>