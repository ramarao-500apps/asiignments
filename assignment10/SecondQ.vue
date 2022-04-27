<template>
  <div>
    <h1>SecondQ</h1>
    <b-form-input
      type="Number"
      id="multiplication"
      placeholder="Enter a Firstnumber"
    ></b-form-input>
    <b-form-input
      type="Number"
      id="divison"
      placeholder="Enter a Secondnumber "
    ></b-form-input>
    <b-button @click="f1()">Multiply</b-button><br /><br />
    <b-button @click="f2()">Divided</b-button>
    <p id="calculation"></p>
  </div>
</template>
<script>
export default {
  name: "SecondQ",
  data() {
    return {
      multiplication: [],
      divison: [],
    };
  },
  methods: {
    f1() {
      document.getElementById("calculation").innerHTML =
        document.getElementById("multiplication").value *
        document.getElementById("divison").value;
      return this.multiplication;
    },
    f2() {
      document.getElementById("calculation").innerHTML =
        document.getElementById("multiplication").value /
        document.getElementById("divison").value;
      return this.divison;
    },
  },
};
</script>