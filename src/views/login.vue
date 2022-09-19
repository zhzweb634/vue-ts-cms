<template>
	<div class="login">login</div>
	<div @click="$router.back()">后退</div>
</template>

<script>
export default {
	name: 'login'
}
</script>

<style scoped lang="less">
.login {
	width: 100px;
	height: 1000px;
	background: sienna;
}
</style>
