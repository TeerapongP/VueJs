<template>
    <main class="mx-auto max-w-2xl py-20 px-4 md:px-0 bg-zinc-900">
        <h1 class="font-black text-3xl md:text-4xl mb-10">Body Mass Index Calculator</h1>
        <form @submit.prevent="onSubmit" @reset="onReset">
            <div>
                <label for="weight" class="block mt-2 mb-3 text-xl font-medium text-white	 ">Weight
                    (Kg)</label>
                <input type="number" id="weight" min="0" max="200" v-model="form.weight"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 text-xl"
                    required>
            </div>
            <div>
                <label for="height" class="block mt-3 mb-4 text-xl font-medium text-white">Height
                    (Cm)</label>
                <input type="number" id="height" min="50" max="220" v-model="form.height"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 text-xl"
                    required>
            </div>
            <button type="submit"
                class="text-white text-xl mt-5 bg-blue-500 hover:bg-blue-800 focus:outline-none focus:ring-4 focus:ring-blue-300 font-medium rounded-full text-sm px-12 py-2.5 text-center mr-2 mb-2 dark:bg-blue-800 dark:hover:bg-blue-500 dark:focus:ring-blue-800">Submit
            </button>
            <div class="result-output mt-8 text-green-600">
                <p class="text-6xl ">{{ response.bmi.toFixed(2) }} </p>
                <p class="mt-3 text-3xl"> {{ response.interpretation }} </p>
            </div>
        </form>
    </main>
</template>
<script>
import axios from 'axios'
import NavBar from '../components/NavBar.vue';
export default {
    name: "IndexPage",
    data() {
        return {
            form: {
                weight: 0,
                height: 0,
            },
            response: {
                weight: 0,
                height: 0,
                bmi: 0,
                interpretation: ""
            },
        };
    },
    methods: {
        onSubmit(event) {
            this.callAPICalculateBMI();
        },
        onReset(event) {
        },
        callAPICalculateBMI() {
            let param = "weight=" + this.form.weight + "&height=" + this.form.height;
            let apiUrl = "https://pirun.ku.ac.th/~faaspsu/edu/mobile/evaluatebmi.php?" + param;
            axios.get(apiUrl).then(res => {
                this.response.weight = res.data.bmidata.weight;
                this.response.height = res.data.bmidata.height;
                this.response.bmi = res.data.bmidata.bmi;
                this.response.interpretation = res.data.bmidata.interpretation;
                console.log(JSON.stringify(this.response));
            });
        }
    },
    components: { NavBar }
}
</script>
    
<style scoped>
body {
    background-color: #1a1a1a;
    color: white;
    font-family: "Karla", sans-serif;
}
</style>