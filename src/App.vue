<script setup lang="ts">
	import { onBeforeMount } from "vue";
	import {
		VPdfViewer,
		type ToolbarOptions,
		useLicense,
	} from "@vue-pdf-viewer/viewer";
	import AppPdfViewer from "./components/AppPdfViewer.vue";

	const toolbarOptions: Partial<ToolbarOptions> | false = false;

	const pdfSrc =
		"https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf";

	onBeforeMount(() => {
		useLicense("YOUR_LICENSE_KEY");
	});
</script>

<template>
	<div>
		<h1>VPV Starter Toolkit: Vue + Composition API + TypeScript</h1>
		<br />
		<h2>Default Toolbar</h2>
		<div class="pdf-viewer-wrapper">
			<VPdfViewer :src="pdfSrc" />
		</div>
		<h2>Without Toolbar</h2>
		<div class="pdf-viewer-wrapper">
			<VPdfViewer
				:src="pdfSrc"
				:toolbar-options="toolbarOptions" />
		</div>
		<h2>Mobile</h2>
		<div class="pdf-viewer-wrapper-mobile">
			<VPdfViewer :src="pdfSrc" />
		</div>
		<AppPdfViewer
			:src="pdfSrc"
			title="Shared Component" />
	</div>
</template>

<style scoped>
	.pdf-viewer-wrapper {
		width: 1028px;
		height: 700px;
		margin: 0 auto;
	}

	.pdf-viewer-wrapper-mobile {
		width: 468px;
		height: 700px;
		margin: 0 auto;
	}
</style>
