<template>
  <div class="bg-white shadow-md rounded-lg p-6 flex flex-col md:flex-row ">
    <!-- Left Part: Profile Picture -->
    <div class="md:w-1/4 p-4 flex justify-center items-start">
      <ProfileImage :name="name" :profileImage="profileImage" />
    </div>

    <!-- Right Part: Profile Information -->
    <div class="md:w-3/4 p-4">
      <div class="flex items-center justify-between mb-4 ">
        <div class="text-center md:text-left">
          <h1 class="text-2xl font-semibold">{{ name }}</h1>
        </div>
        <div class="flex space-x-2">
          <!-- Display spoken languages with round flag icons -->
          <div v-for="(language, index) in spokenLanguages" 
            :key="index" 
            class="rounded-full bg-blue-100 w-8 h-8 hidden md:inline"
            :style="{ backgroundImage: `url(${language.flag})`, backgroundSize: 'cover', backgroundPosition: 'center center' }">
          </div>
        </div>
      </div>

      <!-- Abilities (Tags) Component -->
      <TagsSection :tags="abilities" :maxTags="6"/>

      <!-- Description -->
      <p class="mt-4 text-center md:text-left">{{ description }}</p>

      <!-- Buttons -->
      <div class="mt-4 text-center md:text-left">
        <button class="bg-red-500 text-white px-5 py-2 rounded-full hover:bg-red-600 ">
          BOOK NOW
        </button>
        <a href="#" class="ml-4 text-blue-800 font-semibold hidden md:inline">EXPLORE PROFILE</a>
      </div>


    </div>
  </div>
</template>

<script>
// Import your TagsSection component
import TagsSection from "./TagsSections.vue";
import ProfileImage from "./ProfileImage.vue";
export default {
  props: {
    name: String,
    profileImage: String,
    spokenLanguages: Array,
    abilities: Array,
    description: String,
  },
  components: {
    TagsSection,
    ProfileImage,
   
  },
};
</script>


<style scoped>
/* Additional component-specific styles go here */
</style>
