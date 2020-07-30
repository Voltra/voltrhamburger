<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png" />

		<Menu/>
	</div>
</template>

<script>
import Menu from "@/components/Menu";

export default {
	name: "Home",
	components: {
		Menu,
	}
};
</script>
