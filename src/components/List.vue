<template>
  <div>
    <ul>
      <li
        class="row"
        v-for="(user, index) in list[0]"
        :key="index"
        @click="goToDetails(user.id, user.name)"
      >
        <span>{{ user.id }}</span
        ><span>{{ user.name }}</span
        ><span>{{ user.email }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  namne: "List",
  props: {
    list: Array,
  },
  methods: {
    goToDetails(userId, userName) {
      this.$emit("user-details", { id: userId, name: userName });
    },
  },
};
</script>

<style scoped>
.row {
  padding: 10px;
  border: 1px solid blue;
  margin: 5px;
  cursor: pointer;
}
</style>