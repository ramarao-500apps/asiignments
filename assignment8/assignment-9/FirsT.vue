<template>
  <div id="app">
    <b-table :items="items" :fields="fields"></b-table>
  </div>
</template>
	<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      fields: ["id", "name"],
      items: [
        {
          id: "0",
          name: " Agile CRM",
          description: " A company of excellence",
        },
        { id: "1", name: "mantra technologies", description: "500apps" },
        {
          id: "2",
          name: "500apps Python",
          description: "Backend built using python",
        },
        { id: "3", name: "500apps infinity", description: "Builtusing vue JS" },
      ],
    };
  },
  methods: {},
};
</script> 