<template>
  <div>
    <p> FIfth </p>
    <button @click="fun()">click here</button>
  </div>
</template>
<script>
export default {
  name: "FIfth",
  data() {
    return {
      mycolor: ["Red", "Green", "White", "Black"],
    };
  },
  methods: {
    fun() {
      document.write(
        this.mycolor +
          "<br>" +
          this.mycolor.join("+") +
          "<br>" +
          this.mycolor.join(" ")
      );
    },
  },
};
</script>
