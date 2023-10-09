<template>
  <div>
    <h2 class="text-lg font-semibold">{{ title }}</h2>
    <div class="flex flex-wrap mt-2">
      <!-- Display up to 5 tags and "+X More" tag if there are extra tags -->
      <div
        v-for="(tag, index) in visibleTags"
        :key="index"
        class="flex items-center space-x-2 mb-2 mr-2"
      >
        <div
          class="bg-red-100 rounded-full h-36px px-6 py-2 text-white font-bold text-14px"
        >
          <font-awesome-icon :icon="tag.icon" class="text-red-500" />
          <span class="ml-2 text-red-500 font-bold text-14px">{{ tag.name }}</span>
        </div>
      </div>

      <!-- Display "+X More" tag if there are extra tags -->
      <div v-if="extraTags.length > 0" class="flex items-center space-x-2 mb-2 mr-2">
        <div
          class="bg-red-100 rounded-full h-36px px-6 py-2 text-red-500 font-bold text-14px"
        >
          <span>+{{ extraTags.length }} More</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome"; // Import FontAwesomeIcon
import { library } from "@fortawesome/fontawesome-svg-core";
import {
  faMedkit,
  faCar,
  faLanguage,
  faMapMarker,
  faClock,
  faUserTie,
} from "@fortawesome/free-solid-svg-icons";

// Add Font Awesome icons to the library
library.add(faMedkit, faCar, faLanguage, faMapMarker, faClock, faUserTie);

export default {
  components: {
    FontAwesomeIcon, // Register FontAwesomeIcon component
  },
  props: {
    title: String,
    tags: Array,
  },
  computed: {
    visibleTags() {
      // Return up to 5 tags or all available tags if there are fewer than 5
      return this.tags.slice(0, 5);
    },
    extraTags() {
      // Return extra tags beyond the first 5
      return this.tags.slice(5);
    },
  },
};
</script>


