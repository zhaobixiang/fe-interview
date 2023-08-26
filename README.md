<template>
  <div class="conic"></div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
@keyframes rotate {
  0% {
    transform: rotate(80deg);
  }
	100% {
		transform: rotate(-280deg);
	}
}

.conic {
	position: relative;
	z-index: 0;
	width: 400px;
	height: 240px;
	margin: 20px;
	border-radius: 4px;
	overflow: hidden;
	padding: 2rem;

	&::before {
		content: '';
		position: absolute;
		z-index: -2;
		left: -50%;
		top: -50%;
		width: 200%;
		height: 200%;
		// background-color: #1a232a;
		background-repeat: no-repeat;
		background-position: 0 0;
		background-image: conic-gradient(rgb(8, 193, 235), transparent 30%);
    transform: rotate(80deg);
		animation: rotate 4s linear infinite;
    clip-path: inset();
	}

	&::after {
		content: '';
		position: absolute;
		z-index: -1;
		left: 4px;
		top: 4px;
		width: calc(100% - 8px);
		height: calc(100% - 8px);
		background: #fff;
		border-radius: 2px;
	}
}
</style>
