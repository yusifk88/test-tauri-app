<template>

  <v-row>
    <v-col cols="12" sm="6" class="mx-auto">
      <v-card variant="outlined" class="mt-3">
        <v-card-title>
          testing tauri plugins
        </v-card-title>
        <v-card-text>
          <v-text-field variant="outlined" label="Name" v-model="name"></v-text-field>
          <v-btn @click="testSQLGet" block color="green" variant="flat" size="x-large">Test SQL Select</v-btn>

          <v-btn class="mt-4" @click="testsSQLInsert" block color="green" variant="flat" size="x-large">Test SQL Insert
          </v-btn>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>

</template>
<script lang="ts">
import {defineComponent} from 'vue'
import Database from "tauri-plugin-sql-api";

export default defineComponent({
  name: "TestPluginsComponent",
  data(){
    return{
      name:""

    }
  },

  computed: {
    async DB() {
      return await Database.load("sqlite:test.db");
    }
  },
  methods: {

    async testsSQLInsert() {
      const DB = await Database.load("sqlite:test.db");

      DB.execute("insert into users (name) VALUES ($1)",[
         this.name
      ])
          .then(res => {
            console.log(res, "Success");
          })
          .catch(error => {
            console.log(error, "failed");
          })


    },
    async testSQLGet() {


      const DB = await Database.load("sqlite:test.db");

     DB.select("select * from users ")
        .then(res => {
          console.log(res, "Success");
        })
        .catch(error => {
          console.log(error, "failed");
        })



    }
  }
})
</script>


<style scoped>

</style>
<script setup lang="ts">
</script>