<template>
	<div :class="menuClass">
		<div class="menu__content menu__content--shape">
			<!-- <DEMO> -->
			<nav class="menu__nav">
				<ul class="menu__list">
					<li class="menu__list-item">
						<a href="#">Lorem ipsum dolor sit amet</a>
					</li>

					<li class="menu__list-item">
						<a href="#">Ut aliquet lorem vitae</a>
					</li>

					<li class="menu__list-item">
						<a href="#">Nunc vel ornare sapien</a>
					</li>
				</ul>
			</nav>
			<!-- </DEMO> -->
		</div>

		<div class="menu__opener">
			<Hamburger ref="hamburger" class="menu__button" :opened="opened" @close="onClose" @open="onOpen"/>
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
				return `menu menu--round ${this.extraClasses}`;
			},
		},
		methods: {
			triggerClick(e){
				const { hamburger } = this.$refs;
				hamburger.toggle(e);
			},
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