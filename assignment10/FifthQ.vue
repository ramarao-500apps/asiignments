<template>
  <div>
    <h1>FifthQ</h1>
    <b-form-input
      v-model="value"
      placeholder="Enter Country name"
    ></b-form-input>
    <b-button variant="primary" @click="getData()">Get Data</b-button>
    <b-card v-for="value in items" :key="value.domains" class="mb-2">
      <b-card-text>university_name:-- {{ value.university_name }} </b-card-text>
      <p>domains:--{{ value.domains }}</p>
      <p>website_url:--{{ value.website_url }}</p>
      <p>state_province:--{{ value.state_province }}</p>
    </b-card>
  </div>
</template>
<script>
export default {
  name: "FifthQ",
  data() {
    return {
      value: "",
      items: [],
      res: [],
    };
  },
  methods: {
    async getData() {
      const response = await fetch(
        "http://universities.hipolabs.com/search?country=" + this.value,
        {
          method: "GET",
        }
      );
      const responseText = await response.json();
      this.items = responseText.map((row) => {
        return {
          university_name: row.name,
          domains: row.domains,
          website_url: row.web_pages,
          state_province: row["state_province"],
        };
      });
    },
  },
};
</script>