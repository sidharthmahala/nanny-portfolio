<template>
    <div class="relative">
      <img :src="profileImage" :alt="name" class="w-209 h-209 rounded-full" />
      <img src="star.png" :alt="t" class="absolute bottom-0 right-0 w-15 h-15" />
    </div>
  </template>
  
  <script>
  export default {
    props: {
      name: String,
      profileImage: String,
    },
  };
  </script>
  