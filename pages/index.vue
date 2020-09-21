<template>
    <v-ons-navigator :page-stack="pages" :options="options"></v-ons-navigator>
</template>

<script>
import Page from "@/components/Page";

export default {
    data() {
        return {
            pages: [Page],
	        options: null
        }
    },
	created() {
    	this.$nuxt.$on('push-page', this.pushPage)
		this.$nuxt.$on('pop=page', this.popPage)
	},
	methods: {
    	pushPage($el, data = {}, option = {
		    animation: 'slide',
		    animationOptions: {
			    duration: 0.2,
			    delay: 1,
			    timing: 'ease-in'
		    }
	    }) {
    		this.options = option
		    this.pages.push({
			    extends: $el,
			    data() {
				    return data
			    }
		    })
	    },
		popPage() {
			this.pages.pop()
		}
	},
	destroyed() {
    	this.$nuxt.$off('push-page')
		this.$nuxt.$off('pop-page')
	}
}
</script>