<template>
	<v-ons-page>
		<div class="content">
			<h2>{{ $options.name }}</h2>
			<div class="toggle">
				<div>
					<input type="checkbox" v-model="dialFlg" id="dialFlg_checkbox" />
					<label for="dialFlg_checkbox">floating button flag</label>
				</div>
				<div>
					<input type="checkbox" v-model="itemFlg" id="itemFlg_checkbox" />
					<label for="itemFlg_checkbox">item flag</label>
				</div>
			</div>
			<v-ons-speed-dial
				position="bottom right" direction="up"
					:visible="dialFlg"
					:open.sync="itemFlg">

				<v-ons-fab>
					<v-ons-icon icon="md-face"></v-ons-icon>
				</v-ons-fab>

				<v-ons-speed-dial-item
					v-for="(icon, name) in shareItems"
					:key="name"
					@click="$ons.notification.confirm(`Share on ${name}?`)">
					<v-ons-icon :icon="icon"></v-ons-icon>
				</v-ons-speed-dial-item>

			</v-ons-speed-dial>
		</div>
	</v-ons-page>

</template>

<script>
export default {
	name: "SpeedDial",
	data() {
		return {
			dialFlg: true,
			itemFlg: true,
			shareItems: {
				'Twitter': 'md-twitter',
				'Facebook': 'md-facebook',
				'Google+': 'md-google-plus'
			}
		}
	}
}
</script>

<style scoped>
.content {
	padding-top: 120px;
}

</style>