<template>
  <div class="dashboard-toolbar">
    <Toolbar>
      <template #start>
        <Button icon="pi pi-plus" class="mr-2" severity="secondary" text />
        <Button icon="pi pi-print" class="mr-2" severity="secondary" text />
      </template>

      <template #center>
        <IconField>
          <InputIcon>
            <i class="pi pi-search" />
          </InputIcon>
          <InputText placeholder="Search" />
        </IconField>
      </template>
    </Toolbar>
  </div>
</template>

<script setup lang="ts">
import Toolbar from "primevue/toolbar";
import Button from "primevue/button";
import IconField from "primevue/iconfield";
import InputIcon from "primevue/inputicon";
import InputText from "primevue/inputtext";
</script>

<style scoped>
.dashboard-toolbar {
  width: 100%;
}

:deep(.p-toolbar) {
  width: 100%;
  border-radius: 0;
}
</style>
