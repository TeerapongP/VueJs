<template>
  <b-card>
    <h1>Basal Metabolic Rate (BMR)</h1>
    <b-form @submit.prevent="onSubmit" @reset="onReset">
      <b-form-group Id="input-group-1" label="Your Weight (KG) :" label-for="input-weight">
        <b-form-input id="input-weight" v-model="form.weight" placeholder="Input your weight">
        </b-form-input>
      </b-form-group>
      <b-form-group Id="input-group-2" label="Your Height (CM) :" label-for="input-height">
        <b-form-input id="input-height" v-model="form.height" placeholder="Input your height">
        </b-form-input>
      </b-form-group>
      <b-form-group Id="input-group-3" label="Your age (Year) :" label-for="input-age">
        <b-form-input id="input-age" v-model="form.age" placeholder="Input your age">
        </b-form-input>
      </b-form-group>
      <b-form-group id="input-group-4" label="Your Gender:" label-for="input-gender">
        <b-form-radio-group v-model="form.gender" id="input-gender">
          <b-form-radio value="Male">Male</b-form-radio>
          <b-form-radio value="Female">Female</b-form-radio>
        </b-form-radio-group>
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
        height: 0,
        weight: 0,
        age: 0,
      },
      response: {
        gender: "",
        height: 0,
        weight: 0,
        age: 0,
        bmr: 0,
        interpretation: '',
        unit: ''
      }
    }
  },

  methods: {
    onSubmit(event) {
      this.calculateBMR();
    },
    onReset(event) {
    },
    calculateBMR() {
      if (this.form.gender.toUpperCase() == 'MALE') {
        this.response.bmr = (10 * this.form.weight) + (6.25 * this.form.height) - (5 * this.form.age) + 5;
      }
      else if (this.form.gender.toUpperCase() == 'FEMALE') {
        this.response.bmr = (10 * this.form.weight) + (6.25 * this.form.height) - (5 * this.form.age) -161;
      }
      else this.response.bmr =-1;
      console.log('BMR=' + this.response.bmr);
    }
  }
}
</script>
