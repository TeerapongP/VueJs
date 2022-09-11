<template>
  <b-card>
    <h1>Example VueJS: Input Form using Bootstrap-Vue Framework</h1>
    <b-form @submit.prevent="onSubmit" @reset="onReset">
      <b-form-group Id="input-group-1" label="Your Name:" label-for="input-name">
        <b-form-input id="input-name" v-model="form.name" placeholder="Input your name">
        </b-form-input>
      </b-form-group>
      <b-form-group id="input-group-2" label="Your Gender:" label-for="input-gender">
        <b-form-radio-group v-model="form.gender" id="input-gender">
          <b-form-radio value="Male">Male</b-form-radio>
          <b-form-radio value="Female">Female</b-form-radio>
        </b-form-radio-group>
      </b-form-group>
      <b-form-group id="input-group-3" label="Hobbies:" label-for="input-hobbies">
        <b-form-checkbox-group v-model="form.hobbies" id="input-hobbies">
          <b-form-checkbox value="Reading">Reading</b-form-checkbox>
          <b-form-checkbox value="Listening">Listening a Music</b-form-checkbox>
          <b-form-checkbox value="Watching">Watching a TV</b-form-checkbox>
          <b-form-checkbox value="Gaming">Playing game</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>
      <b-button type="submit" variant="primary">Submit</b-button>
    </b-form>
  </b-card>
</template>
<script>
export default {
  data() {
    return {
      form: {
        gender: "",
        name: "",
        hobbies: []
      }
    }
  },

  methods: {
    onSubmit(event) {
      alert(JSON.stringify(this.form))
      //console.log(JSON.stringify(this.form))
    },
    onReset(event) {
    }
  }
}
</script>
