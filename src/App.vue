<template>
	<div>
		<router-link to="/">home</router-link>
		<router-link to="/login">login</router-link>

		<router-view v-slot="{ Component, route }">
			<text>{{ route.fullPath }}</text>
			<transition name="slide-fade">
				<keep-alive>
					<component :is="Component" />
				</keep-alive>
			</transition>
		</router-view>

		<HelloWorld></HelloWorld>
	</div>
</template>

<script lang="ts">
import HelloWorld from 'components/HelloWorld.vue'
export default {
	components: { HelloWorld }
}
</script>

<style lang="less">
.slide-fade-enter-active {
	transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
	transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
	transform: translateX(20px);
	opacity: 0;
}
.exact-active-class {
	color: red;
}
</style>
