<template>
	<div>
		<h2>Dialog</h2>
		<h3>use ons notification</h3>
		<v-ons-button class="button" @click="$ons.notification.alert('Hello, world!')">alert</v-ons-button>
		<v-ons-button class="button" @click="$ons.notification.confirm('Hello, world!')">confirm</v-ons-button>
		<v-ons-button class="button" @click="$ons.notification.prompt('Hello, world!')">prompt</v-ons-button>
		<h3>use components</h3>
		<v-ons-button class="button" @click="dialogFlag = true">normal dialog</v-ons-button>
		<v-ons-button class="button" @click="alertSlotFlag = true">alert (slots)</v-ons-button>
		<v-ons-button class="button" @click="alertPropsFlag = true">alert (props)</v-ons-button>

		<v-ons-dialog cancelable :visible.sync="dialogFlag" :options="{ animation: 'none'}">
			<div class="normal">Hello, World!</div>
		</v-ons-dialog>

		<v-ons-alert-dialog modifier="rowfooter" :visible.sync="alertSlotFlag">
			<span slot="title">Title slot alert</span>
			<span>Hello, World</span>
			<template slot="footer">
				<v-ons-alert-dialog-button @click="alertSlotFlag = false">Cancel</v-ons-alert-dialog-button>
				<v-ons-alert-dialog-button @click="alertSlotFlag = false">Ok</v-ons-alert-dialog-button>
			</template>
		</v-ons-alert-dialog>

		<v-ons-alert-dialog
			modifier="rowfooter"
			:title="'Title props alert'"
			:footer="{
				        Cancel: () => { this.alertPropsFlag = false },
                        Ok: () => { this.alertPropsFlag = false }
                    }"
			:visible.sync="alertPropsFlag">
			<span>Hello, World!</span>
		</v-ons-alert-dialog>
	</div>
</template>

<script>
export default {
	data() {
		return {
			dialogFlag: false,
			alertSlotFlag: false,
			alertPropsFlag: false
		}
	}
}
</script>

<style lang="scss" scoped>
.normal {
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100px;
}
</style>