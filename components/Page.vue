<template>
    <v-ons-page>
        <v-ons-toolbar>
            <div class="center">{{ $options.name }}</div>
        </v-ons-toolbar>
	    <div class="content">
		    <v-ons-list class="list">
			    <v-ons-list-item class="item" tappable @click="moveTo(0)">Carousel</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(1)">Control</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(2)">Dialog</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(3)">Form</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(4)">Gesture</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(5)">Grid</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(6)">List</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(7)">Menu</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(8)">Navigation</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(9)">Page</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(10)">Tabbar</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(11)">Util</v-ons-list-item>
			    <v-ons-list-item class="item" tappable @click="moveTo(12)">Visual</v-ons-list-item>
		    </v-ons-list>
	    </div>
    </v-ons-page>
</template>

<script>
import Carousel from "@/components/Carousel";
import Control from '@/components/Control'
import Dialog from "@/components/Dialog";

export default {
    name: "Page",
	data() {
    	return {
    		pages:[Carousel, Control, Dialog]
	    }
	},
	methods: {
    	moveTo(pageIndex) {
			this.$nuxt.$emit('push-page', this.pages[pageIndex])
	    }
	}
}
</script>

<style lang="scss" scoped>
.content {
	margin-top: 10px;
}
.list {
	.item {
		border-bottom: 1px solid #d4d4d4;
	}
}
</style>
