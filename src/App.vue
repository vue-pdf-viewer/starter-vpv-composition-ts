<script setup lang="ts">
  import { VPdfViewer, type ToolbarOptions } from '@vpv/viewer';
  const toolbarOptions: Partial<ToolbarOptions> | false = false
</script>

<template>
  <div>
    <h1>VPV Starter Toolkit</h1>
    <h2>Default Toolbar</h2>
    <div class="pdf-viewer-wrapper">
      <VPdfViewer
        src="https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf" />
    </div>
    <h2>Without Toolbar</h2>
    <div class="pdf-viewer-wrapper">
      <VPdfViewer src="https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf"
        :toolbar-options="toolbarOptions" />
    </div>
  </div>
</template>

<style scoped>
  .pdf-viewer-wrapper {
    width: 1028px;
    height: 700px;
  }
</style>
