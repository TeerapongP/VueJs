<template>
  <div>
    <h1>Example VueJS: Input Form</h1>
    <label for="name">Name</label>
    <input id="name" v-model="name" placeholder="input your name" />
    <p>Gender</p>
    <div>
      <input type="radio" id="male" value="Male" v-model="gender" />
      <label for="male">Male</label><br />
      <input type="radio" id="female" value="Female" v-model="gender" />
      <label for="female">Female</label>
    </div>
    <p>Hobbies</p>
    <div>
      <input type="checkbox" id="reading" value="Reading" v-model="hobbies" />
      <label for="reading">Reading</label><br />
      <input type="checkbox" id="listening" value="Listening" v-model="hobbies" />
      <label for="listening">Listening a Music</label><br />
      <input type="checkbox" id="watching" value="Watching" v-model="hobbies" />
      <label for="watching">Watching a TV</label><br>
      <input type="checkbox" id="gaming" value="Gaming" v-model="hobbies" />
      <label for="gaming">Playing game</label>
    </div>
    <br />
    <button v-on:click="submit()">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      gender: '',
      name: '',
      hobbies: []
    }
  },
  methods: {
    submit() {
      console.log(this.name, this.gender, this.hobbies)
    }
  }
}
</script>

<style>
@import '../assets/css/index.css';
</style>
