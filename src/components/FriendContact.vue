<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(favorite)" : "" }}</h2>
    <button @click="toggleDetails">Show Details</button>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <ul v-if="detailsAreVisible">
      <li>Age: {{ age }}</li>
      <li>Email: {{ emailAddress }}</li>
      <li>Phone: {{ phoneNumber }}</li>
    </ul>
  </li>
</template>

<script>
export default {  
  props:{
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: Boolean,
      required: true,
      default: false,      
      },
    },
  
  data() {
    return {
      detailsAreVisible: false,   
      
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
      
    },

  },
};
</script>
