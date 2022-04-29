<template>
  <div>
    <h2>{{ userData.id }}</h2>
    <h2>{{ userData.name }}</h2>
  </div>
</template>

<script>
export default {
  name: "UserDetails",
  props: {
    userData: Object,
  },
};
</script>