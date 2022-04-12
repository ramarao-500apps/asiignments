<template>

<div>

<h1>Table view</h1>

<table align="center">

<thead>

<tr>

<th>email</th>

<th>id</th>

<th>name</th>

</tr>

</thead>

<tr v-for="array in array" :key="array.id">

<td>{{ array.email }}</td>

<td>{{ array.id }}</td>

<td>{{ array.name }}</td>

</tr>

<tbody>

</tbody>

</table>

</div>

</template>

<script>

export default {

name: "TablevieW2",

data() {

return {

array: [

{email: "Eliseo@gardner.biz", id: 1, name: "id labore ex et quamlaborum"},

{email: "Jayne_Kuhic@sydney.com", id: 2, name: "quo vero reiciendisvelit similique earum"},

{email: "Nikita@garfield.biz", id: 3, name: "odio adipisci rerumaut animi"},

{email: "Lew@alysha.tv", id: 4, name: "alias odio sit"}

],

};

},

};

</script>

<style scoped>

table {

font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;

border-collapse: collapse;

width: 45%;

background-color: white;

}

td,

th {

border: 5px solid #dddddd;

text-align: left;

padding: 10px;

}

</style>