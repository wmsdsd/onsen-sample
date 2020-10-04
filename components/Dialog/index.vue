<template>
	<v-ons-page>
		<v-ons-toolbar>
			<div class="left">
				<v-ons-back-button></v-ons-back-button>
			</div>
			<div class="center">{{ $options.name }}</div>
		</v-ons-toolbar>
		<div class="content">
			<action-sheet />
			<alert-dialog />
			<modal />
			<pop-over />
			<toast />
		</div>
	</v-ons-page>
</template>

<script>
import ActionSheet from "@/components/Dialog/ActionSheet";
import AlertDialog from "@/components/Dialog/AlertDialog";
import Modal from "@/components/Dialog/Modal";
import PopOver from "@/components/Dialog/PopOver";
import Toast from "@/components/Dialog/Toast";

export default {
	name: "Dialog",
	components: {
		ActionSheet, AlertDialog, Modal, PopOver, Toast
	},
	data() {
		return {
		}
	},
	methods: {
	}
}
</script>

<style lang="scss" scoped>
.content {
	padding: 10px;
}
</style>