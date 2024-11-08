<script setup lang="ts">
	import { VPdfViewer, VPVBaseProps, useLicense } from "@vue-pdf-viewer/viewer";
	import { ref, watch, onBeforeMount } from "vue";

	const props = defineProps({
		...VPVBaseProps,
		title: {
			type: String,
			required: true,
		},
	} as const);

	onBeforeMount(() => {
		useLicense({ licenseKey: "your-license-key" });
	});

	const viewerRef = ref<InstanceType<typeof VPdfViewer> | null>(null);

	watch(viewerRef, (newVal) => {
		console.log("viewerRef", newVal);
	});
</script>
<template>
	<div>
		<h2>
			{{ props.title }}
		</h2>
		<div :style="{ width: '1028px', height: '700px', margin: '0 auto' }">
			<VPdfViewer
				v-bind="props"
				ref="viewerRef" />
		</div>
	</div>
</template>
