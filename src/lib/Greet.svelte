<script lang="ts">
	import { invoke } from '@tauri-apps/api/tauri';

	let name = '';
	let greeting = '';

	async function greet() {
		greeting = await invoke('greet', { name });
	}
</script>

<div>
	<input type="text" id="greet-input" placeholder="Enter a name..." bind:value={name} />
	<button on:click={greet}>Greet</button>
	<p>
		{greeting}
	</p>
</div>
