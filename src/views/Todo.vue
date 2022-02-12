<template>
  <v-container>
    <h1>To do page</h1>
    <h2>เพิ่มหัวข้องาน/การบ้าน</h2>

    <FormTodo @atd="getTodo"></FormTodo>
    <div class="container">
      <v-container>
        <h1>งาน/การบ้าน</h1>
        <v-list flat subheader two-line>
          <v-list-item-group v-model="settingsItem">
            <v-list-item v-for="(item, i) in additems" :key="i">
              <template fluid>
                <v-list-item-action>
                  <v-checkbox></v-checkbox>
                </v-list-item-action>

                <v-list-item-content>
                  <v-list-item-title v-text="item.text"></v-list-item-title>
                </v-list-item-content>
                <v-btn color="warning" @click="deleteTodo(i)">Delete</v-btn>
              </template>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-container>
    </div>
  </v-container>
</template>

<script>
import formTodo from "../components/formTodo.vue";
import FormTodo from "../components/formTodo.vue";

export default {
  data: () => ({
    subject: "",
    work: "",
    SettingsItem: 1,
    additems: [
      { text: "วิชา SE :ออกแบบ diagram" },
      { text: "วิชา SE :ออกแบบ db" },
      { text: "วิชา Web :ออกแบบ ui" },
      { text: "วิชา Web :Assingment100" },
    ],
  }),
  componentsL: { formTodo },
  components: { FormTodo },
  methods: {
    getTodo() {
      console.log("Todo");
      this.additems.push({
        text: this.subject + " " + this.work,
      });
    },
    deleteTodo(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style></style>
