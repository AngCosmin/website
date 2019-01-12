<template>
  <div class="animation-trigger">
	<div class="more-wrap">
	  <div class="more-text">Read more</div>
	  <div class="more-dots">
		<div class="dot dot-1"></div>
		<div class="dot dot-2"></div>
		<div class="dot dot-3"></div>
	  </div>
	</div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default class ReadMore extends Vue {
}
</script>


<style lang="scss" scoped>
	$link-color: #92EAC0;

	.animation-trigger {
		display: flex;
		align-content: center;
		justify-content: center;
		flex-direction: column;
		text-align: center;
		cursor: pointer;
	}

	.more-text {
		display: inline-block;
		padding: 10px 30px;
		border: 2px solid $link-color;
		border-radius: 50px;
		color: lighten($link-color, 10%);
		color: $link-color;
		font-style: italic;
		font-weight: 400;
		letter-spacing: 1px;
		opacity: 0;
		transform: translateY(-10px);
		transition: all .25s ease-out;
		
		
		&:hover {
			background-color: $link-color;
			color: #FFF; // fake transparent color
		}
		
		.animation-trigger:hover & {
			opacity: 1;
			transform: translateY(0);
			transition: all .3s ease-in-out;
		}
	}

	.more-dots {
		transform: translateY(-30px);
		transition: all .3s ease;

		.dot-1 {
			animation: bounce 3s infinite;
		}

		.dot-2 {
			animation: bounce 3.1s infinite;
		}

		.dot-3 {
			animation: bounce 3.2s infinite;
		}

		
		.animation-trigger:hover & {
			transform: translateY(-10px);
			transition: all .3s ease-out;
		}
		
		.dot {
			display: inline-block;
			height: 6px;
			width: 6px;
			border-radius: 50%;
			margin: 0 3px;
			background: $link-color;
			
			.animation-trigger:hover & {
			animation: bounce-3 .8s 1 ease;
			animation-fill-mode: forwards;
			
			&.dot-1 { }
			&.dot-2 { animation-delay: .1s; }
			&.dot-3 { animation-delay: .2s; }
			}
		}
	}

	@keyframes bounce-1 {
		0%, 25% { transform: translate(0, 0) scale(1); }
		50% { transform: translate(0, 30px) scale(.2); background: #DCDCDC; }
		75%, 100% { transform: translate(0, 0) scale(1); opacity: 0; };
	}
	@keyframes bounce-2 {
		0% { transform: translate(0, 0) scale(1); }
		100% { transform: translate(0, 30px) scale(.2); background: #DCDCDC; }
	}
	@keyframes bounce-3 {
		0% { transform: translate(0, 0) scale(1); }
		50% { transform: translate(0, 15px); background: #DCDCDC; }
		70% { transform: translate(0, 13px); };
		100% { opacity: 0; };
	}

	@-webkit-keyframes bounce {
		0%, 20%, 50%, 80%, 100% {-webkit-transform: translateY(0);}	
		40% {-webkit-transform: translateY(-15px);}
		60% {-webkit-transform: translateY(-6px);}
	}
	
	@-moz-keyframes bounce {
		0%, 20%, 50%, 80%, 100% {-moz-transform: translateY(0);}
		40% {-moz-transform: translateY(-15px);}
		60% {-moz-transform: translateY(-6px);}
	}
	
	@-o-keyframes bounce {
		0%, 20%, 50%, 80%, 100% {-o-transform: translateY(0);}
		40% {-o-transform: translateY(-15px);}
		60% {-o-transform: translateY(-6px);}
	}

	@keyframes bounce {
		0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
		40% {transform: translateY(-15px);}
		60% {transform: translateY(-6px);}
	}
</style>
