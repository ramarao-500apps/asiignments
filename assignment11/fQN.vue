<template>
  <div>
    <b-form-select v-model="value" :options="countries"></b-form-select
    ><br /><br />

    <b-button variant="warning" @click="res">Get Data</b-button><br /><br />

    <b-input-group>
      <b-row
        ><b-col cols-mc="12">
          <b-form-input
            id="filter-input"
            v-model="filter"
            type="search"
            placeholder="Type to Search"
          ></b-form-input> </b-col
      ></b-row>

      <b-input-group-append>
        <b-button :disabled="!filter" @click="filter = ''">Clear</b-button>
      </b-input-group-append>
    </b-input-group>

    <b-form-group v-model="sortDirection" v-slot="{ ariaDescribedby }">
      <b-form-checkbox-group
        v-model="filterOn"
        :aria-describedby="ariaDescribedby"
      >
        <b-form-checkbox value="university_name"
          >university_name</b-form-checkbox
        >

        <b-form-checkbox value="domains">domains</b-form-checkbox>

        <b-form-checkbox value="website_url">website_url</b-form-checkbox>

        <b-form-checkbox value="isActive">state_province</b-form-checkbox>
      </b-form-checkbox-group>
    </b-form-group>

    <b-container>
      <b-row cols-md="12">
        <b-table
          :items="items"
          :fields="fields"
          :filter="filter"
          :filter-included-fields="filterOn"
          @filtered="onFiltered"
        ></b-table>
      </b-row>
    </b-container>
  </div>
</template>

<script>
const { getNames } = require("country-list");
export default {
  name: "fQN",

  data() {
    return {
      fields: [],

      items: [],

      value: "",

      countries: [],

      filter: null,

      filterOn: [],
    };
  },

  computed: {
    sortOptions() {
      return this.fields

        .filter((f) => f.sortable)

        .map((f) => {
          return { text: f.label, value: f.key };
        });
    },
  },

  mounted() {
    let countries = getNames();

    this.countries = countries.map((row) => {
      return { value: row, text: row };
    });

    if (this.countries.length) this.value = this.countries[0].text;
  },

  methods: {
    redirect(value) {
      window.open(value, "_blank");
    },

    async res() {
      const response = await fetch(
        "http://universities.hipolabs.com/search?country=" + this.value
      );

      const responseText = await response.json();

      this.items = responseText.map((row) => {
        return {
          university_name: row.name,

          domains: row.domains,

          website_url: row.web_pages,

          state_province: row.state_province,
        };
      });
    },
  },
};
</script>
