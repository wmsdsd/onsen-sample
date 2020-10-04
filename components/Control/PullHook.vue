<template>
	<v-ons-page>
		<div class="content">
			<h2>{{ $options.name }}</h2>
			<v-ons-pull-hook
				:action="pullHookFetch"
				@changestate="state = $event.state">
				<!-- 기본 표시를 삭제 하려면 initial을 삭제 하면 된다. -->
				<span v-show="state === 'initial'"> Pull to refresh </span>
				<span v-show="state === 'preaction'"> Release </span>
				<span v-show="state === 'action'"> Loading... </span>
			</v-ons-pull-hook>

			<v-ons-list>
				<v-ons-list-item v-for="(item, key) in listItem" :key="key">{{item}}</v-ons-list-item>
			</v-ons-list>
		</div>
	</v-ons-page>
</template>

<script>
export default {
	name: "PullHook",
	data() {
		return {
			state: 'initial',
			listItem:[0]

		}
	},
	methods: {
		pullHookFetch(done) {
			setTimeout(() => {
				this.listItem.push(this.listItem.length)
				done()
			}, 1000)
		}
	}
}
</script>

<style scoped>
.content {
	padding-top: 180px;
}
</style>