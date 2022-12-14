<template>
  <section>
    <header><h1>My friends</h1></header>
    <ul>
      <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :id="friend.id"
        :name="friend.name"
        :age="friend.age"
        :email-address="friend.email"
        :phone-number="friend.phone"
        :is-favorite="friend.isFavorite"
        @toggle-favorite="toggleFavorite"
      ></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      friends: [
        {
          id: "Helard",
          name: "Helard Flores",
          age: 30,
          email: "john@gmail.com",
          phone: "555-555-5555",
          isFavorite: true,
        },
        {
          id: "John",
          name: "John Doe",
          age: 25,
          email: "doe@gmail.com",
          phone: "555-555-5555",
          isFavorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavorite(friendId) {
      const friendIndex = this.friends.find((friend) => friend.id === friendId);

      friendIndex.isFavorite = !friendIndex.isFavorite;
    },
  },
};
</script>

<style src="./assets/styles.css"></style>
