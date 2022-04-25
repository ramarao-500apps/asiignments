<template>
  <div>
    hello srikanth
    <h2>message:{{ message }}</h2>
    <h2>name:{{ name }}</h2>
    <h2>number:{{ number }}</h2>
  </div>
</template>
	<script>
export default {
  name: "SriKanth",
  props: {
    message: String,
    name: String,
    number: Number,
  },
  methods: {
    func() {
      alert("hi naveen");
    },
  },
};
</script> 4th 1