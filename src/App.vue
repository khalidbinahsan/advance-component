<script setup>
import Button from './components/Button.vue';
import ButtonCounter from './components/ButtonCounter.vue';
import Location from './components/Location.vue';
import ApplicantDetails from './components/ApplicantDetails.vue'
const data = [
  {
    title: 'Photo by Drew Dao',
    image: 'https://plus.unsplash.com/premium_photo-1669048776605-28ea2e52ae66?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    location: 'California',
    price: 87,
    rating: 3,
    time: 15,
  },
  {
    title: 'Photo by Trent Haaland',
    image: 'https://plus.unsplash.com/premium_photo-1670985849616-6aa6c441e0bf?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    location: 'San Diego, California',
    price: 75,
    rating: 3,
    time: 21,
  },
  {
    title: 'Photo by Alex Kolundzija',
    image: 'https://images.unsplash.com/photo-1714423718253-b1bd2d95ddd9?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    location: 'Sun flare behind a Joshua Tree.',
    price: 59,
    rating: 4,
    time: 14,
  }
]
const peoples = [
  {
    name: 'Margot Foster',
    position: 'Backend Developer',
    email: 'margotfoster@gamil.com',
    salary: '$120,000',
    about: 'Margot Foster Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, quos harum, recusandae ex voluptatem sint aut doloribus, iste minima praesentium labore consequuntur possimus velit. Quos quia adipisci error autem iure!',
    attachments: [
      {
        name: 'resume_back_end_developer.pdf',
        size: '256kb',
        type: 'PDF',
        url: 'https://khalidbinahsan.com'
      },
      {
        name: 'coverletter_back_end_developer.pdf',
        size: '506kb',
        type: 'PDF',
        url: 'https://khalidbinahsan.com'
      }
    ]
  },
  {
    name: 'John Doe',
    position: 'Frontend Developer',
    email: 'johndoe@gamil.com',
    salary: '$105,000',
    about: 'John Doe Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, quos harum, recusandae ex voluptatem sint aut doloribus, iste minima praesentium labore consequuntur possimus velit. Quos quia adipisci error autem iure!',
    attachments: [
      {
        name: 'resume_front_end_developer.pdf',
        size: '346kb',
        type: 'PDF',
        url: 'https://khalidbinahsan.com'
      },
      {
        name: 'coverletter_front_end_developer.pdf',
        size: '268kb',
        type: 'PDF',
        url: 'https://khalidbinahsan.com'
      }
    ]
  },
  {
    name: 'Abir Ahmed',
    position: 'Graphics Designer',
    email: 'abirahmed@gamil.com',
    salary: '$88,000',
    about: 'Abir Ahmed Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, quos harum, recusandae ex voluptatem sint aut doloribus, iste minima praesentium labore consequuntur possimus velit. Quos quia adipisci error autem iure!',
    attachments: [
      {
        name: 'resume_graphics_designer.pdf',
        size: '300kb',
        type: 'PDF',
        url: 'https://khalidbinahsan.com'
      }
    ]
  }
]
</script>

<template>
  <div class="container my-10">
    <div class="flex items-center justify-center mt-5">
      <img class="logo" src="./assets/vue.svg" alt="Vue logo">
      <h1 class="text-2xl">Vue Components</h1>
    </div>
  </div>
<div class="container">
  <section class="flex space-x-10 justify-between">
  <Location v-for="(item, index) in data" :key="index" v-bind="item" />
  </section>
</div>
<section class="my-10">
  <div class="container">
    <!-- Applicant Details will goes here -->
    <ApplicantDetails :applicants="peoples" />
  </div>
</section>
</template>

<style scoped>

</style>
