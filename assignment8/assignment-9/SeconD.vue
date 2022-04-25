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
      fields: ["name", "description", "Yearsofexperience", "Location"],
      items: [
        {
          name: " Agile CRM",
          description: " A company of excellence",
          Yearsofexperience: "12",
          Location: "Hyderabad",
        },
      ],
    };
  },
  methods: {},
};
</script> 