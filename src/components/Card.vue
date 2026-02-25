<template>
  <div class="card" style="width: 25rem; overflow: hidden">
    <Card>
      <template #header>
        <Image
          :src="project.image"
          alt="Project Image"
          style="width: 100%; height: auto; display: block"
          preview
        />
      </template>

      <template #content>
        <Fieldset
          :legend="project.name"
          :pt="{ legend: { style: 'margin-left: 0; margin-right: auto;' } }"
        >
          <p class="m-0">{{ project.description }}</p>
        </Fieldset>
      </template>
    </Card>
  </div>
</template>

<script setup lang="ts">
import Card from "primevue/card";
import Fieldset from "primevue/fieldset";
import Image from "primevue/image";

interface CardProjectData {
  name: string;
  description: string;
  image: string;
}

const props = defineProps<{ project: CardProjectData }>();
</script>
