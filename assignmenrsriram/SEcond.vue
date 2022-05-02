<template>
  <div>
    <P> SEcond </P>
  </div>
</template>

<script>
export default {
  name: "SEcond",
  data() {
    return {
      a: [43, 45, 90, 180],
    };
  },
  merhods: {
    fun() {
      const doubled = this.a.reduce((total, amount) => {
        total.push(amount * 2);

        return total;
      }, []);

      document.write(this.a), document.write("<br> ", doubled);
    },
  },
};
</script>
