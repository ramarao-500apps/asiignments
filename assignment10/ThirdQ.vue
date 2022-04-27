<template>
  <div>
    <h1>ThirdQ</h1>
    <b-table :items="Names" :fields="fields"></b-table>
    <b-form-input
      id="input"
      v-model="text"
      placeholder="Enter text to add into table">
      </b-form-input>
    <b-form-input
      id="input1"
      v-model="text"
      placeholder="Enter text to add into table"
    ></b-form-input>
    <b-button @click="add()">CLICK TO ADD</b-button><br /><br />
    <b-button @click="remove()">DELETE ROW</b-button>
  </div>
</template>
<script>
export default {
  name: "QuestioN3",
  data() {
    return {
      Names: [{ firstname: "Agile", lastname: "CRM" }],
      fields: ["firstname", "lastname"],
    };
  },
  methods: {
    add() {
      this.Names.push({
        firstname: document.getElementById("inp").value,
        lastname: document.getElementById("inp1").value,
      });
    },
    remove() {
      this.Names.shift();
    },
  },
};
</script>
