<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <ol>
      <li v-for="person in people">name: {{ person.name }} bio: {{ person.bio }}</li>
    </ol>
    <p>name:<input type="text" v-model="newPerson.name"></p>
    <p>bio:<input type="text" v-model="newPerson.bio"></p>
    <p><button v-on:click="addPerson()">Click to add new person</button></p>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to your people app!",
      people: [
        {name: "joe", bio: "a dude", bioVisible: "true"},
        {name: "jane", bio: "a lady person", bioVisible: "true"},
        {name: "jack", bio: "a fella", bioVisible: "true"}
      ],
      newPerson: {name: "", bio: ""}
    };
  },
  created: function() {},
  methods: {
    addPerson: function() {
      console.log('adding new person');
      this.people.push(this.newPerson);
    }
  },
  computed: {}
};
</script>