<template>
  <section>
    <h2>My friends</h2>
    <ul>
      <li v-for="friend in friends" :key="friend.id">
        <h3>{{ friend.name }}</h3>
        <p>Age: {{ friend.age }}</p>
        <p>Email: {{ friend.email }}</p>
        <p>Phone: {{ friend.phone }}</p>
      </li>
    </ul>
  </section>
  
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      friends: [
        { 
          id:'Helard',
          name: 'Helard Flores',
          age: 30,
          email: 'john@gmail.com',
          phone: '555-555-5555'
        },
        { 
          id:'John',
          name: 'John Doe',
          age: 25,
          email: 'doe@gmail.com',
          phone: '555-555-5555'
        }],
    };
  },
  components: {
    
  }

  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
