<template>
  <div>
    <NannyProfile
      name="Alexandra K."
      profileImage="profile-image.png"
      :spokenLanguages="spokenLanguages"
      :abilities="abilities"
      description="👋🏻 Reliable and with a strong motivation to grow professionally in the education sector, she knows how to take care of tasks assigned with commitment and resoluteness, always acting in compliance with the feedback and recommendations of colleagues and above with a view to continuous improvement."
    />
  </div>
</template>

<script>
import NannyProfile from "./components/NannyProfile.vue";

export default {
  components: {
    NannyProfile,
  },
  data() {
    return {
      spokenLanguages: [
        { name: "Italian", flag: "Italian-flag.jpg" },
        { name: "English", flag: "English-flag.jpg" },
        { name: "German", flag: "German-flag.jpg" },
        // Add more languages here
      ],
      abilities: [
        { name: "First Aid", icon: ["fas", "fa-medkit"] }, // Use Font Awesome icons as an array
        { name: "Owns a Car", icon: ["fas", "fa-car"] },
        { name: "Multilingual", icon: ["fas", "fa-language"] },
        { name: "Traveler", icon: ["fas", "fa-user-tie"] },
        { name: "First Aid", icon: ["fas", "fa-medkit"] }, // Use Font Awesome icons as an array
        { name: "Owns a Car", icon: ["fas", "fa-car"] },
        { name: "Multilingual", icon: ["fas", "fa-language"] },
        { name: "Traveler", icon: ["fas", "fa-user-tie"] },
      ],
    };
  },
};
</script>