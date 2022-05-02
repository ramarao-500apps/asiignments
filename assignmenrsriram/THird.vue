<template>
  <div>
    <P> THird </P>
    <button @click="fun()">click here</button>
  </div>
</template>

<script>
export default {
  name: "THird",
  data() {
    return {
      list: [1, 1, 2, 2, 2, 3, 4, 3, 2],
    };
  },
  methods: {
    fun() {
      let unique = this.list.filter(
        (item, index, array) => array.indexOf(item) === index
      );

      document.write(unique);
    },
  },
};
</script>