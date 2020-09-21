<template>
    <v-ons-page>
        <v-ons-toolbar>
            <div class="center">{{ $options.name }}</div>
        </v-ons-toolbar>

        <v-ons-list class="list">
            <v-ons-list-item class="item" tappable @click="moveTo(0)">Carousel</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Control</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Dialog</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Form</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Gesture</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Grid</v-ons-list-item>
            <v-ons-list-item class="item" tappable>List</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Menu</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Navigation</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Page</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Tabbar</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Util</v-ons-list-item>
            <v-ons-list-item class="item" tappable>Visual</v-ons-list-item>
        </v-ons-list>

    </v-ons-page>
</template>

<script>
import Carousel from "./Carousel";

export default {
    name: "Page",
	data() {
    	return {
    		pages:[Carousel]
	    }
	},
    created() {
        console.log(this)
    },
	methods: {
    	moveTo(pageIndex) {
			this.$nuxt.$emit('push-page', this.pages[pageIndex])
	    }
	}

}
</script>

<style lang="scss">
.list {
	.item {
		border-bottom: 1px solid #d4d4d4;
	}
}
</style>
