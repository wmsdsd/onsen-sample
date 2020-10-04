<template>
	<v-ons-page>
		<v-ons-toolbar>
			<div class="left">
				<v-ons-back-button></v-ons-back-button>
			</div>
			<div class="center">{{ $options.name }}</div>
		</v-ons-toolbar>
		<div class="content">
			<v-ons-toolbar class="toolbar">
				<div class="center">
					<h2>Segment</h2>
					<v-ons-segment
						class="segment"
						tabbar-id="tabbar"
						:index.sync="segmentIndex">
						<button>pull-hook</button>
						<button>speed-dial</button>
					</v-ons-segment>
				</div>
			</v-ons-toolbar>

			<v-ons-tabbar
				id="tabbar"
				:index.sync="tabIndex">
				<template slot="pages">
					<pull-hook></pull-hook>
					<speed-dial></speed-dial>
				</template>

				<v-ons-tab></v-ons-tab>
				<v-ons-tab></v-ons-tab>
			</v-ons-tabbar>
		</div>
	</v-ons-page>
</template>

<script>
import PullHook from "./PullHook"
import SpeedDial from "./SpeedDial";

export default {
	name: "Control",
	components: {
		PullHook, SpeedDial
	},
	data() {
		return {
			segmentIndex: 0,
			tabIndex: 0
		}
	},
	methods: {
	}
}
</script>

<style lang="scss" scoped>
.content {
	margin: 20px;


	.toolbar {
		height: 120px;
	}

	.segment {
		width: 80%;
	}
}
</style>