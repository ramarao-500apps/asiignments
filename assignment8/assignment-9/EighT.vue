<template>
  <div>
    <h2>QeighT</h2>
    <button @click="f2()">Submit</button>
  </div>
</template>
	<script>
var officers = [
  { id: 20, name: "Captain Piett" },
  { id: 24, name: "General Veers" },
  { id: 56, name: "Admiral Ozzel" },
  { id: 88, name: "Commander Jerjerrod" },
];

export default {
  name: "QeighT",
  methods: {
    f2() {
      let index = officers.filter((r) => {
        return r.id == 24;
      });
      console.log(index);
    },
  },
};
</script>