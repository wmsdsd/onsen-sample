<template>
	<div class="content-modal">
		<h2>Modal</h2>
		<v-ons-button class="button" @click="showModal()">show modal</v-ons-button>

		<v-ons-modal :visible="modalFlag" @click="modalFlag = false">
			<div class="background"></div>
			<div class="content">
				<div style="text-align: center">
					<p>Loading <v-ons-icon icon="fa-spinner" spin></v-ons-icon></p>
					<br>
					<p>Click and close modal</p>
				</div>
			</div>
		</v-ons-modal>
	</div>
</template>

<script>
export default {
	data() {
		return {
			modalFlag: false,
		}
	},
	methods: {
		showModal() {
			this.modalFlag = true
		}
	}
}
</script>

<style scoped>

</style>