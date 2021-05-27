<template>
  <ejs-dropdownlist
    id="dropdownlist"
    :itemTemplate="itemTemplate"
    :dataSource="sportsData"
    :fields="fields"
    placeholder="Select a game"
  ></ejs-dropdownlist>
</template>

<script>
import { DropDownListComponent } from "@syncfusion/ej2-vue-dropdowns";

import { createApp } from "vue";

const app = createApp({
  // Displays "Hello, World" initially, changes based on input
  template: '<hello></hello>'
}); 

// Register the `hello` component
var itemVue = app.component('itemTemplate', {
  data: () => ({}),
  template:`<span><span class='name'>{{data.Game}}</span><span class ='city'>{{data.Id}}</span></span>`
});  
 
export default {
  name: "App",
  components: {
    'ejs-dropdownlist' : DropDownListComponent,
  },
  data() {
    return {
      sportsData: [
        { Id: "game1", Game: "Badminton" },
        { Id: "game2", Game: "Football" },
        { Id: "game3", Game: "Tennis" },
      ],
      fields: { text: "Game", value: "Id" },
      itemTemplate:  function() {
        return { template: itemVue };
      }
    };
  },
};
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-dropdowns/styles/material.css";

button {
  margin: 25px 5px 20px 20px;
}
</style>
