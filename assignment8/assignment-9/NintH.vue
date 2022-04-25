<template>
  <div>
    <h2>QnintH</h2>
    <button @click="fun()">Submit</button>
  </div>
</template>
	<script>
export default {
  name: "QnintH",
  data() {
    return {
      a: [14, 2, "x"],
      b: [4, "b", 6],
    };
  },
  mounted() {
    this.b = [...this.a, ...this.b];
  },
  methods: {
    fun() {
      alert(this.a);
    },
  },
};
</script>