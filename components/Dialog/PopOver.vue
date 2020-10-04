<template>
	<div>
		<h2>Popover</h2>
		<div class="popover-button">
			<v-ons-button @click="showPopover($event, 'right')">right</v-ons-button>
			<v-ons-button @click="showPopover($event, 'up')">up</v-ons-button>
			<v-ons-button @click="showPopover($event, 'left')">left</v-ons-button>
		</div>

		<v-ons-popover cancelable
		               class="popover-content"
		               :visible.sync="popoverVisible"
		               :target="popoverTarget"
		               :direction="popoverDirection"
		               :cover-target="coverTarget">
			<p>{{ popoverDirection }}</p>
		</v-ons-popover>
	</div>
</template>

<script>
export default {
	data() {
		return {
			popoverVisible: false,
			popoverTarget: null,
			popoverDirection: 'up',
			coverTarget: false
		}
	},
	methods: {
		showPopover(event, direction) {
			this.popoverTarget = event;
			this.popoverDirection = direction;
			this.coverTarget = false;
			this.popoverVisible = true;
		}

	}
}
</script>

<style lang="scss" scoped>
.popover {
	&-button {
		display: flex;
		justify-content: space-between;
	}

	&-content {
		p {
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100px;
		}
	}
}
</style>