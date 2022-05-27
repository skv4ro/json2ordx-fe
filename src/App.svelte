<script>
	import * as ace from "ace-builds"
	import "ace-builds/src-noconflict/theme-monokai"
	import "ace-builds/src-noconflict/mode-xml"
	import "ace-builds/src-noconflict/ext-searchbox"
	import { onMount } from "svelte"

	export let prd

	onMount(() => {
		const editor = ace.edit(prd);
		editor.setOption('useWorker', false)
		editor.setTheme('ace/theme/monokai')
		editor.session.setMode('ace/mode/xml')
	})	
</script>

<main>
	<div id={prd} class="editor"></div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.editor {
		width: 40%;
		height: 500px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>