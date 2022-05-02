<template>
  <div>
    <p> FIrst </p>
    <p>{{ diameter() }}</p>

    <p>{{ perimeter() }}</p>
  </div>
</template>

<script>
export default {
  name: "FIrst",

  data() {
    return {
      radius: 20,

      perimeter: () => 2 * Math.PI * this.radius,
    };
  },

  methods: {
    diameter() {
      const circle = {
        radius: 20,
      };

      console.log(circle);

      return this.radius * 2;
    },
  },
};
</script>