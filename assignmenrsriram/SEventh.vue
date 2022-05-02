<template>
  <div>
    <p> SEventh </p>
    <button @click="fun()">click here</button>
  </div>
</template>

<script>
export default {
  name: "SEventh",

  data() {
    return {
      arr1: [3, "a", "a", "a", 2, 3, "a", 3, "a", 2, 4, 9, 3],
    };
  },

  methods: {
    fun() {
      document.write([...new Set(this.arr1)]);
    },
  },
};
</script>