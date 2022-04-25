<template>
  <div>
    <button @click="func">Result</button>
  </div>
</template>

<script>
export default {
  name: "QtentH",

  data() {
    return {
      array: [
        { id: 20, name: "Captain Piett" },

        { id: 24, name: "General Veers" },

        { id: 56, name: "Admiral Ozzel" },

        { id: 88, name: "Commander Jerjerrod" },
      ],
    };
  },

  methods: {
    func() {
      var result = this.array.map((x) => x.id);
      document.write(result);
    },
  },
};
</script>