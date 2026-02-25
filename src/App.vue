<script setup lang="ts">
import Button from "primevue/button";
import Card from "./components/Card.vue";

const cardProjectData = {
  name: "Project Name",
  description: "This is a description of the project.",
  image: "https://via.placeholder.com/400x300",
};
</script>

<template>
  <div>
    <h1>the_sandbox</h1>
    <Button label="Click me" />
    <Card :project="cardProjectData" />
  </div>
</template>

<style scoped></style>
