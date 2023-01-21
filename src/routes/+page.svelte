<script>
	import JSConfetti from 'js-confetti';
	import { onMount } from 'svelte';
	import AnimText from '$lib/AnimText.svelte';
	import { fade } from 'svelte/transition';

	let text = 'Ку ку)';
	let n = 0;
	let repeat_button = false;

	function animate({ mes, delay, _confetti, _confettiNumber, _confettiRadius, rep }) {
		if (mes) {
			n = n + delay;
			setTimeout(() => {
				text = mes;
			}, n);
		}

		if (_confetti) {
			setTimeout(() => {
				const jsConfetti = new JSConfetti();
				jsConfetti.addConfetti({
					confettiRadius: _confettiRadius,
					confettiNumber: _confettiNumber ? _confettiNumber : 250
				});
			}, n);
			n = n + delay;
		}
		if (rep) {
			n = n + delay;
			setTimeout(() => {
				repeat_button = rep;
			}, n);
		}
	}

	onMount(() => {
		animate({ mes: 'Вітаю тебе з днем народження 🎉', delay: 3000, rep: false });
		animate({ mes: 'Бажаю всього найкращого', delay: 6000 });
		animate({ mes: 'Щоб ти завжди була усміхнена 😊', delay: 5000 });
		animate({ mes: 'Щоб всі твої плани на майбутнє здійснилися🌟', delay: 5000 });
		animate({ mes: 'Щоб друзі та рідні завжди були поруч 🫂', delay: 6000 });
		animate({ mes: 'Щоб вчилась тільки на високі бали 👩‍🎓', delay: 5000 });
		animate({ mes: 'Щоб кохана людина завжди підтримувала тебе в усьому👩‍❤️‍👨', delay: 6000 });
		animate({
			mes: 'Щоб в житті ти робила те що хочеш 😋 і це приносило чималий прибуток 💸',
			delay: 7000
		});
		animate({
			mes: 'А найголовніше щоб ти була здорова 😇 та залишалася такою якою ти є',
			delay: 8500
		});
		animate({ mes: 'Красивою 👑', delay: 7000 });
		animate({ mes: 'Веселою 😄', delay: 3000 });
		animate({ mes: 'Кмітливою 🤓', delay: 3000 });
		animate({ mes: 'Стильною 💅', delay: 3000 });
		animate({ mes: 'Та вміючую завжди підтримати 🫶', delay: 3000 });
		animate({ mes: "Пам'ятай ти найкраща і в тебе все вийде 🤍", delay: 5000 });
		animate({ mes: 'З Днем нараодження 🥳', delay: 7000, _confetti: true, _confettiRadius: 5 });
		animate({ rep: true, delay: 3000 });
	});
</script>

<svelte:head>
	<title>Congrats</title>
</svelte:head>

<section class="flex my-auto flex-col justify-center items-center gap-72">
	<AnimText {text} font_size={'200rem'} />

	{#if repeat_button}
		<button
			in:fade={{ duration: 500 }}
			onClick="window.location.reload()"
			class=" text-black bg-white rounded-lg flex items-center justify-center w-auto h-[40px] "
			><span class="symbol py-1 px-2.5 font-thin text-[1.2rem]">re-play</span></button
		>
	{/if}
</section>

<style scoped>
	button {
		filter: drop-shadow(0px 0px 5px#fff);
		animation: pulsee 2s infinite;
	}

	.symbol {
		filter: drop-shadow(0px 0px 10px #000);
	}

	@keyframes pulsee {
		0% {
			filter: drop-shadow(0px 0px 10px #fff);
		}
		50% {
			filter: drop-shadow(0px 0px 8px #fff);
		}
		100% {
			filter: drop-shadow(0px 0px 10px #fff);
		}
	}
</style>
