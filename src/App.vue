<script>
export default {
  data() {
    return {
      weight: 0,
      height: 0,

      you: "",
      two: "",
      three: ""
    };
  },
  computed: {
    bmi() {
      if (this.weight && this.height) {
        return this.weight / this.height ** 2;
      }

      if (this.weight <= 50) {
        this.you = "Your under weight";
      } else if (this.weight >= 50) {
        this.you = " Your healthly";
      }

      if (this.height <= 1.7) {
        this.two = "your too short";
      } else if (this.height >= 1.7) {
        this.two = " your tall";
      }

      return 0;
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="holder">
      <h1>BMI Calculator</h1>
      <div class="in">
        <label for="weight">Weight (kg):</label>
        <input class="enter" type="number" v-model="weight" />
      </div>
      <div class="in">
        <label for="height">Height (m):</label>
        <input class="enter" type="number" id="height" v-model="height" />
      </div>
      <p class="info" v-if="bmi">Your BMI is: {{ bmi }}</p>
      <p v-if="weight" class="info">{{ you }}</p>
      <p v-if="height" class="info">{{ two }}</p>
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 70vh;
}

.holder {
  display: inline;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: grey;
  padding: 20px;
  border: 2px solid black;
  border-radius: 20px;
}

h1 {
  display: flex;
  border-bottom: 2px solid;
  margin-bottom: 20px;
  width: 220px;
}

.in {
  display: block;
  width: 100%;
}

label {
  display: flex;
  justify-content: center;
  margin-bottom: 2px;
  font-size: 30px;
}

.enter {
  display: flex;
  margin-left: 15%;
  border-radius: 10px;
  padding: 5px;
  outline: none;
  border: none;
  color: #ffff;
  background-color: black;
}

p {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
  margin-bottom: -30px;
}
</style>