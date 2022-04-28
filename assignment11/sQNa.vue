<template>
  <div>
    <b-container>
      <b-form-select v-model="value" :options="countries"> </b-form-select>
      <b-button @click="country">Submit</b-button>

      <b-pagination
        v-model="currentPage"
        :total-rows="fun"
        :per-page="perPage"
        aria-controls="my-table"
      ></b-pagination>

      <b-row cols-md="12">
        <b-table
          id="my-table"
          :per-page="perPage"
          :current-page="currentPage"
          striped
          hover
          :items="items"
        >
          <b-col
            ><p>university name: {{ value.university_name }}</p></b-col
          >

          <b-col
            ><p>domains: {{ value.domains }}</p></b-col
          >

          <a :href="value.website_url" _target="blank">{{
            value.website_url
          }}</a>

          <b-col
            ><p>state province: {{ value.state_province }}</p></b-col
          >
        </b-table>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import axios from "axios";
const { getNames } = require("country-list");
export default {
  name: "MahI",

  data() {
    return {
      perPage: 4,

      currentPage: 1,

      value: "",

      countries: [],

      items: [],
    };
  },

  mounted() {
    let countries = getNames();

    this.countries = countries.map((row) => {
      return { value: row, text: row };
    });
  },

  methods: {
    redirect(user) {
      window.open(user, "_blank");
    },

    async country() {
      const response = await axios.get(
        "http://universities.hipolabs.com/search?country=" + this.value
      );

      const responseText = await response.data;

      console.log("response", responseText);

      this.items = responseText.map((row) => {
        return {
          domains: row.domains,

          website_url: row.web_pages[0],

          location: row.country,
        };
      });
    },
  },

  computed: {
    fun() {
      return this.items.length;
    },
  },
};
</script>