<template>
	<div>
		<h2>Toast</h2>
		<div>
			<v-ons-button
				class="button"
				@click="$ons.notification.toast(
				'Hi there!',
				{
					timeout: 1000,
					animation: 'fall'
				})">
				<span>Queue notification toast (top)</span>
			</v-ons-button>
			<v-ons-button class="button" @click="toastVisible = !toastVisible">Toggle element toast (bottom)</v-ons-button>
		</div>

		<v-ons-toast :visible.sync="toastVisible" animation="ascend">
			<span>toast message</span>
			<button @click="toastVisible = false">ok</button>
		</v-ons-toast>
	</div>
</template>

<script>
export default {
	data() {
		return {
			toastVisible: false
		}
	}
}
</script>

<style scoped>
.button {
	margin: 10px 0;
}
</style>