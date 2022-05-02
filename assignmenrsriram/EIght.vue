<template>
  <div>
    <P> EIght </P>
    <button @click="fun()">click here</button>
  </div>
</template>

<script>
export default {
  name: "EIght",
  data() {
    return {
      color: ["Blue ", "Green", "Red", "Orange", "Violet", "Indigo", "Yellow "],
    };
  },
  method: {
    fun() {
      var o = ["th", "st", "nd", "rd"],
        x = n % 100;
      return x + (o[(x - 20) % 10] || o[x] || o[0]);
    },
  },
};
</script>