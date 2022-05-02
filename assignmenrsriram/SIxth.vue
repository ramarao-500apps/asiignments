<template>
  <div>
    <P> SIxth </P>
    <button @click="fun()">click here</button>
  </div>
</template>

<script>
export default {
  name: "SIxth",
  data() {
    return {
      arr1: [3, "a", "a", "a", 2, 3, "a", 3, "a", 2, 4, 9, 3],
    };
  },
  methods: {
    fun() {
      var mf = 1;
      var m = 0;
      var item;
      for (var i = 0; i < this.arr1.length; i++) {
        for (var j = i; j <this.arr1.length; j++) {
          if (this.arr1[i] == this.arr1[j]) m++;
          if (mf < m) {
            mf = m;
            item = this.arr1[i];
          }
        }
        m = 0;
      }
      document.write(item + " ( " + mf + " times ) ");
    },
  },
};
</script>
