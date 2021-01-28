<template>
  <div class="new-note">
    <h1 style="color: #402caf; font-weight: bold">Notes App</h1>
    <h1 style="margin-top: 25px">Title</h1>
    <div class="inputs"><input v-model="note.title" />
      <div class="choosen">
      </div>
    </div>

    <h1>Description</h1>
    <textarea v-model="note.descr"></textarea>
    <button class="btn btnPrimary" @click="addNote">Add note</button>
  </div>
</template>

<script>
export default {
  props: {
    note: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addNote() {
      this.$emit("addNote", this.note);
    },
  },
};
</script>

<style lang="scss">
.new-note {
  text-align: center;
  margin-top: 10px;
}
.btn {
  margin-top: 20px;
}
</style>