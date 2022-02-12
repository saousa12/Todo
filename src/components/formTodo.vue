<template>
  <v-container>
    <v-col class="d-flex">
      <v-select
        :items="items"
        v-model="subject"
        label="Select"
        solo
        required
      ></v-select>
    </v-col>

    <v-col>
      <v-text-field
        v-model="work"
        label="Outlined"
        outlined
        clearable
      ></v-text-field>
    </v-col>
    <v-btn class="mr-4" @click="addTodo" color="primary">Add</v-btn>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      subject: "",
      work: "",
      items: ["วิชา SE", "วิชา Web", "วิชา ML", "อื่นๆ"],
    };
  },
  methods: {
    addTodo() {
      //console.log("click add todo");
      console.log(this.subject + " " + this.work);
      this.$emit("atd", this.addTodo);
    },
  },
};
</script>

<style></style>
