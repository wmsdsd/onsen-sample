<template>
	<v-ons-page>
		<v-ons-toolbar>
			<div class="left">
				<v-ons-back-button></v-ons-back-button>
			</div>
			<div class="center">{{ $options.name }}</div>
		</v-ons-toolbar>
		<div class="content">
			<div class="carousel">
				<div class="carousel-default">
					<p>carousel default</p>
					<div
						class="carousel-default__left"
						@click="defaultIndex > 0 ? defaultIndex-- : defaultIndex = 2">
						<v-ons-icon
							icon="md-chevron-left"
							size="50px, material: 50px"
							style="color: white"></v-ons-icon>
					</div>
					<div
						class="carousel-default__right"
						@click="defaultIndex < 2 ? defaultIndex++ : defaultIndex = 0">
						<v-ons-icon
							icon="md-chevron-right"
							size="50px, material: 50px"
							style="color: white"></v-ons-icon>
					</div>
					<v-ons-carousel
						class="carousel-default__block"
						:index.sync="defaultIndex">
						<v-ons-carousel-item
							class="carousel-default__item"
							v-for="(img, key) in images"
							:key="key">
							<img
								:src="img"
								alt="image" />
						</v-ons-carousel-item>
					</v-ons-carousel>
				</div>

				<div class="carousel-swipe">
					<p>carousel swipe</p>
					<v-ons-carousel
						class="carousel-swipe__block"
						:index.sync="swipeIndex"
						swipeable
						auto-scroll>
						<v-ons-carousel-item
							class="carousel-swipe__item"
							v-for="(img, key) in images"
							:key="key">
							<img
								:src="img"
								alt="image" />
						</v-ons-carousel-item>
					</v-ons-carousel>
					<div class="carousel-swipe__dot">
						<div v-for="(dot, n) in images" :style="{'background-color':n === swipeIndex ? 'white': null }"></div>
					</div>
				</div>

				<div class="carousel-card">
					<p>card card</p>
					<v-ons-carousel
						class="carousel-card__block"
						:index.sync="cardIndex"
						swipeable
						auto-scroll>
						<v-ons-carousel-item
							class="carousel-card__item"
							v-for="(img, key) in images"
							:key="key">
							<img
								:src="img"
								alt="image" />
						</v-ons-carousel-item>
					</v-ons-carousel>
				</div>
			</div>
		</div>
	</v-ons-page>
</template>

<script>
export default {
	name: "Carousel",
	data() {
		return {
			images: [
				require('~/assets/image/cat.jpg'),
				require('~/assets/image/old-man.jpg'),
				require('~/assets/image/rose-beetle.jpg')
			],
			defaultIndex: 0,
			swipeIndex: 0,
			cardIndex: 0
		}
	}
}
</script>

<style lang="scss" scoped>
.carousel {

	p {
		text-align: center;
		margin: 30px 0 10px;
	}

	&-default {

		&__left {
			left: 10px;
		}

		&__right {
			right: 10px;
		}

		&__left, &__right {
			position: absolute;
			z-index: 1;
			padding-top: 90px;
		}


		&__item {
			img {
				width: 100%;
			}
		}
	}

	&-swipe {
		&__item {
			img {
				width: 100%;
			}
		}
		&__dot {
			display: flex;
			justify-content: center;
			align-content: center;

			div {
				width: 10px;
				height: 10px;
				border-radius: 10px;
				border: 1px solid gray;
				background-color: gray;
				margin: 0 10px;
			}
		}
	}

	&-card {
		width: 100%;
		&__block {
			width: 100%;
			padding: 0 20px;
		}
		&__item {
			padding: 0 10px;
			img {
				width: 100%;
			}
		}
	}
}
</style>
