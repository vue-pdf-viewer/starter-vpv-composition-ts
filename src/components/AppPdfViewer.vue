<script setup lang="ts">
	import { VPdfViewer, VPVBaseProps } from "@vue-pdf-viewer/viewer";
	import { ref, watch } from "vue";

	const props = defineProps({
		...VPVBaseProps,
		title: {
			type: String,
			required: true,
		},
	} as const);

	const viewerRef = ref<InstanceType<typeof VPdfViewer> | null>(null);

	watch(viewerRef, (newVal) => {
		if (newVal) {
			console.log("These are VPV instance properties", Object.keys(newVal));
		}
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
