<template>
  <div>
    <P> FOurth </P>
    <button @click="fun()">click here</button>
  </div>
</template>

<script>
export default {
  name: "FOurth",
  data() {
    return {};
  },
  methods: {
    fun() {
      var array = function (input) {
        if (toString.call(input) == "[object Array]") return true;
        return false;
      };
      console.log(array("w3resource"));
      console.log(array([1, 2, 4, 0]));
    },
  },
};
</script>