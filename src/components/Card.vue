<template>
  <div class="project-card">
    <div class="card-image-wrapper">
      <Image
        :src="project.image"
        alt="Project Image"
        class="card-image"
        preview
      />
      <div class="image-overlay" />
    </div>

    <div class="card-body">
      <Fieldset
        :legend="project.name"
        :pt="{
          root: { class: 'project-fieldset-root' },
          legend: { class: 'project-fieldset-legend' },
          legendLabel: { class: 'project-fieldset-legend-label' },
          content: { class: 'project-fieldset-content' },
        }"
        :unstyled="true"
      >
        <p class="card-description">{{ project.description }}</p>
      </Fieldset>
    </div>
  </div>
</template>

<script setup lang="ts">
import Image from "primevue/image";
import Fieldset from "primevue/fieldset";

interface CardProjectData {
  name: string;
  description: string;
  image: string;
}

const props = defineProps<{ project: CardProjectData }>();
</script>

<style scoped>
.project-card {
  width: 22rem;
  border-radius: 20px;
  overflow: hidden;
  background: var(--p-surface-card);
  box-shadow:
    0 1px 2px rgba(0, 0, 0, 0.04),
    0 4px 16px rgba(0, 0, 0, 0.08),
    0 12px 40px rgba(0, 0, 0, 0.06);
  transition:
    transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1),
    box-shadow 0.3s ease;
  font-family: -apple-system, "Helvetica Neue", sans-serif;
  cursor: pointer;
}

.project-card:hover {
  transform: translateY(-4px) scale(1.01);
  box-shadow:
    0 2px 4px rgba(0, 0, 0, 0.08),
    0 8px 24px rgba(0, 0, 0, 0.14),
    0 20px 56px rgba(0, 0, 0, 0.12);
}

/* Image */
.card-image-wrapper {
  position: relative;
  width: 100%;
  aspect-ratio: 16 / 10;
  overflow: hidden;
  background: var(--p-surface-100);
}

.card-image :deep(img) {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.project-card:hover .card-image :deep(img) {
  transform: scale(1.04);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    transparent 50%,
    rgba(0, 0, 0, 0.08) 100%
  );
  pointer-events: none;
}

.card-body {
  padding: 1.1rem 1.2rem 1.3rem;
}

:deep(.project-fieldset-root) {
  border: 1.5px solid var(--p-surface-border);
  border-radius: 12px;
  padding: 0;
  margin: 0;
  background: transparent;
}

:deep(.project-fieldset-legend) {
  display: flex;
  align-items: center;
  margin-left: 0.75rem;
  margin-top: -0.65rem;
  padding: 0 0.35rem;
  background: var(--p-surface-card);
  width: fit-content;
}

:deep(.project-fieldset-legend-label) {
  font-size: 1.05rem;
  font-weight: 600;
  color: var(--p-text-color);
  letter-spacing: -0.02em;
  line-height: 1.3;
  font-family: -apple-system, "Helvetica Neue", sans-serif;
  white-space: nowrap;
}

:deep(.project-fieldset-content) {
  padding: 0.6rem 0.85rem 0.85rem;
}

.card-description {
  font-size: 0.875rem;
  color: var(--p-text-muted-color);
  margin: 0;
  line-height: 1.6;
  letter-spacing: -0.005em;
  font-family: -apple-system, "Helvetica Neue", sans-serif;
}
</style>
