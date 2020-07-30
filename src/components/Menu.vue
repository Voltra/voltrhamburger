<template>
	<div :class="menuClass">
		<div class="menu__content menu__content--shape"></div>

		<div class="menu__opener">
			<Hamburger class="menu__button" :opened="opened" @close="onClose" @open="onOpen"/>
		</div>
	</div>
</template>

<script>
	import Hamburger from "@/components/Hamburger"

	export default {
		components: {
			Hamburger,
		},
		data() {
			return {
				opened: false,
				extraClasses: "",
			};
		},
		computed: {
			menuClass(){
				return `menu ${this.extraClasses}`;
			},
		},
		methods: {
			onClose() {
				this.opened = false;
				this.extraClasses = "";
			},
			onOpen() {
				this.opened = true;
				this.extraClasses = "opened";
			},
		},
	}
</script>

<style lang="scss" scoped>
	@use "~@/scss/components/Menu" as *;
</style>