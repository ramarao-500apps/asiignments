<template>
  <div>
    <b-card align="center">
      <b-card-text>
        <p v-for="Info in Infos" :key="Info.id">
          {{ Info.text }}

          {{ Info.Description }}
        </p>
      </b-card-text>
    </b-card>
  </div>
</template>


<script>
export default {
  name: "QsixtH",

  data() {
    return {
      Infos: [
        {
          text: "Name : AgileCRM ",
          Description: "Description : A Company of Excellence",
        },

        {
          text: "Name : Mantra Technologies",
          Description: "Description : 500Apps",
        },

        {
          text: "Name : 500apps Python",
          Description: "Description : Backend built using Python",
        },

        {
          text: "Name : 500apps Infinity",
          Description: "Description : Built Using Vue.JS",
        },
      ],
    };
  },
};
</script>