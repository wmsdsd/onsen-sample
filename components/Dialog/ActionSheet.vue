<template>
	<div>
		<h2>Action Sheet</h2>
		<v-ons-button class="button" @click="$ons.openActionSheet(
				{
					buttons: ['label1', 'label2', 'label3'],
					title: 'Lorem ipsum',
					cancelable: true,
					destructive: 1
				})">Dynamic Action Sheet</v-ons-button>
		<v-ons-button class="button" @click="actionSheetFlag = true">Static Action Sheet</v-ons-button>

		<v-ons-action-sheet
			:visible.sync="actionSheetFlag"
			cancelable
			title="Description">
			<v-ons-action-sheet-button icon="md-square-o">Label 1</v-ons-action-sheet-button>
			<v-ons-action-sheet-button icon="md-square-o" modifier="destructive">Label 2</v-ons-action-sheet-button>
			<v-ons-action-sheet-button icon="md-square-o">Label 3</v-ons-action-sheet-button>
		</v-ons-action-sheet>
	</div>
</template>

<script>
export default {
	data() {
		return {
			actionSheetFlag: false
		}
	}
}
</script>

<style scoped>
.button {
	margin: 10px 0;
}
</style>