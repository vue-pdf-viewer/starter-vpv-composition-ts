<script setup lang="ts">
  import { VPdfViewer, VPVBaseProps } from '@vue-pdf-viewer/viewer';

  const props = defineProps({
      ...VPVBaseProps, 
      title: {
        type: String,
        required: true
      }
    } as const
  )
</script>
<template>
  <div>
    <h2>
      {{ props.title }}
    </h2>
    <div :style="{ width: '1028px', height: '700px', margin: '0 auto'}">
      <VPdfViewer v-bind="props" />
    </div>
  </div>
</template>