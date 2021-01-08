<template>
  <v-dialog width="600" v-model="dialog" persistent v-bind="$attrs" v-on="$listeners">
    <template v-for="(_, slot) of $scopedSlots" v-slot:[slot]="scope">
      <slot :name="slot" v-bind="scope" :open="open"/>
    </template>

    <v-card>
      <v-card-text>
        <v-text-field v-model="data" label="Data:"></v-text-field>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="red" dark text @click="dialog = false">Cancel</v-btn>

        <v-btn color="primary" dark text @click="save">Save</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "VEditor",
  props: {
    value: String
  },
  data() {
    return {
      dialog: false,
      data: JSON.parse(JSON.stringify(this.value))
    };
  },
  methods: {
    save() {
      this.$emit("input", this.data);
      this.dialog = false;
    },
    open() {
      this.dialog = true;
    }
  }
};
</script>
