<script lang="ts" src="./sketchfab"></script>

<template>
	<div class="devlog-post-sketchfab-embed">
		<app-responsive-dimensions :ratio="16 / 9">
			<a v-if="!isHydrated || !isShowing" @click="play">
				<div class="play-button-overlay">
					<app-jolticon icon="play" />
				</div>

				<div
					class="devlog-post-sketchfab-embed-thumb"
					:style="{ 'background-image': `url( '${sketchfab.thumbnail_url}')` }"
				/>
			</a>
			<app-sketchfab-embed v-else :sketchfab-id="sketchfab.sketchfab_id" autoplay />
		</app-responsive-dimensions>
	</div>
</template>

<style lang="stylus" scoped>
@import '../../variables'
@import '~styles-lib/mixins'
.devlog-post-sketchfab
	&-embed
		rounded-corners-lg()
		change-bg('bg-offset')
		margin-top: $-item-padding-xs-v
		margin-left: -($-item-padding-xs)
		margin-right: -($-item-padding-xs)
		position: relative
		@media $media-sm-up
			margin-top: $-item-padding-v
			margin-left: -($-item-padding-container)
			margin-right: -($-item-padding-container)
		a
			display: block
		&-thumb
			position: absolute
			top: 0
			right: 0
			bottom: 0
			left: 0
			background-repeat: no-repeat
			background-position: center center
			background-size: cover
</style>
