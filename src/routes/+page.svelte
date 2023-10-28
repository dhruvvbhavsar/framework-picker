<script lang="ts">
	import {
		siNextdotjs,
		siReact,
		siNuxtdotjs,
		siVuedotjs,
		siGatsby,
		siAstro,
		siPython,
		siAngular,
		siSvelte,
		siCocacola
	} from 'simple-icons';
	import { slide } from 'svelte/transition';
	import * as ease from 'svelte/easing';
	const arr = [
		{
			icon: siNextdotjs.svg,
			name: 'Next Js',
			color: '#ffffff'
		},
		{
			icon: siReact.svg,
			name: 'React',
			color: '#61DAFB'
		},
		{
			icon: siNuxtdotjs.svg,
			name: 'Nuxt Js',
			color: '#00DC82'
		},
		{
			icon: siSvelte.svg,
			name: 'Svelte',
			color: '#ff3e00'
		},
		{
			icon: siVuedotjs.svg,
			name: 'Vue Js',
			color: '#4FC08D'
		},
		{
			icon: siGatsby.svg,
			name: 'Gatsby',
			color: '#663399'
		},
		{
			icon: siAstro.svg,
			name: 'Astro',
			color: '#BC52EE'
		},
		{
			icon: siPython.svg,
			name: 'Python',
			color: '#3776AB'
		},
		{
			icon: siAngular.svg,
			name: 'Angular',
			color: '#DD0031'
		},
		{
			icon: siCocacola.svg,
			name: 'Coca Cola',
			color: '#ED1C16'
		}
	];
	let state = 'framework';
	let color = '#ffffff';

	function updateState(s: string, c: string) {
		state = s;
		color = c;
	}
</script>

<div class="flex justify-center items-center h-screen w-full bg-black text-white">
	<div class="grid grid-cols-6 grid-rows-2 w-5/6 mx-auto h-72">
		<div class="col-span-2 border-dotted border border-[#2e2e2e]">
			<div class="h-full text-3xl font-bold my-10 ml-8">
				<div>
					<div class="flex gap-2">
						Your
						{#key state}
							<p style="color: {color};" in:slide={{ duration: 150, easing: ease.circIn }}>
								{state + ','}
							</p>
						{/key}
					</div>
					<p>Your way.</p>
				</div>
			</div>
		</div>
		{#each arr as { icon, color, name }}
			<!-- svelte-ignore a11y-no-static-element-interactions -->
			<div
				on:mouseleave={() => updateState('framework', '#ffffff')}
				on:mouseenter={() => updateState(name, color)}
				class="col-span-1 border-dotted border border-[#2e2e2e]"
			>
				<!-- display icon -->
				<div class={` w-10 h-full flex flex-col justify-center mx-auto invert`}>
					{@html icon}
				</div>
			</div>
		{/each}
	</div>
</div>
