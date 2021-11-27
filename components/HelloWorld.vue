<template>
	<div class="game">
		<div class="game__wrapper">
			<header class="game__header header">
				<div class="header__container _container">
					<v-menu></v-menu>
				</div>
			</header>
			<div class="game__body body-game">
				<div class="body-game__container _container">
					<div class="body-game__player player">
						<div class="player__name fas fa-user">Player 1</div>
						<div class="player__count">Count: {{ botCount }}</div>
					</div>
					<v-board></v-board>
					<div class="body-game__player player">
						<div class="player__name fas fa-user">Player 2</div>
						<div class="player__count">Count: {{ playerCount }}</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import vMenu from '@/components/vMenu';
import vBoard from '@/components/vBoard';

import { mapGetters } from 'vuex';

export default {
	name: "HelloWorld",
	components: {
		vMenu,
		vBoard
	},
	computed: mapGetters(['botCount', 'playerCount'])
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

$minWidth: 320px;
$maxWidth: 1920px;
$maxWidthContainer: 1300;
$md1: $maxWidthContainer;
$md2: 991.98;
$md3: 767.98;

body {
	color: #fff;
	font-size: 14px;
	font-family: "Arial";
	&._lock {
		overflow: hidden;
	}
}

._container {
	max-width: $maxWidthContainer + px;
	margin: 0 auto;
	padding: 0px 20px;
}
.header {
	background-color: #3b3a3a;
	&__container {
		min-height: 70px;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		
	}
}
.game {
	background-color: #313131;
	min-height: 100vh;
	width: 100%;
	font-family: 'Arial';
	&__wrapper {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}
	
	&__body {
		padding: 30px 0px 20px 0px;
		flex: 1 1 auto;
		height: 100%;
	}
	
}

.body-game {

	display: flex;
	flex-direction: column;
	&__container {
		display: flex;
		flex: 1 1 auto;
		flex-direction: column;
		width: 100%;
	}


	&__board {
		flex: 1 1 auto;
		margin: auto;
		padding: 40px 0px;
	}
}
.player {
	text-align: center;

	&__name {
		font-size: 18px;
		line-height: 24px;
		margin: 0px 0px 5px 0px;
		&::before {
			margin: 0px 12px 0px 0px;
		}
	}
	&__count {

	}
}

</style>
