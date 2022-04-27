<template>
  <div>
    <center>
      <h2>FourthQ</h2>
      <input
        type="Text"
        id="Input"
        @keyup="search()"
        placeholder="Search here"
        title="Type in a name"/>

      <table id="Table">
        <ul>
          <tr>
            <td>Orange</td>
          </tr>
          <tr>
            <td>Red</td>
          </tr>
          <tr>
            <td>Blue</td>
          </tr>
          <tr>
            <td>Black</td>
          </tr>
          <tr>
            <td>White</td>
          </tr>
        </ul>
      </table>
    </center>
  </div>
</template>
<script>
export default {
  name: "FourthQ",
  data() {
    return {
      array_names: ["orange", "red", "blue", "black", "white"],
      input: "",
      filter: "",
      table: "",
    };
  },
  methods: {
    search() {
      this.input = document.getElementById("Input");
      this.filter = this.input.value.toUpperCase();
      this.table = document.getElementById("Table");
      this.tr = this.table.getElementsByTagName("tr");
      for (this.i = 0; this.i < this.tr.length; this.i++) {
        this.td = this.tr[this.i].getElementsByTagName("td")[0];
        if (this.td) {
          this.txtValue = this.td.textContent || this.td.innerText;
          if (this.txtValue.toUpperCase().indexOf(this.filter) > -1) {
            this.tr[this.i].style.display = "";
          } else {
            this.tr[this.i].style.display = "none";
          }
        }
      }
    },
  },
};
</script>