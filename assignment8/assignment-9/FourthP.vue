<template>
  <div class="hello">
    <h1>QfourtH</h1>

    <QfourtH :message="message" :name="name" :number="number"></QfourtH>
  </div>
</template>
	<script>
import QfourtH from "./QfourtH.vue";
export default {
  name: "QfourtH",
  components: {
    QfourtH,
  },
  data() {
    return {
      message: "hi",
      name: "rohith",
      number: 123,
    };
  },
};
</script>