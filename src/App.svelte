<script>
	import ListInvoice from './ListInvoice.svelte';
	const amount = 25
	let amountPrint = `${amount} $`;
	const dolares = () => {
		amountPrint = `${amount} $`;
	} 
	const cordoba = () => {
		amountPrint = `${amount * 35} c$`;
	}
	const listInvoice = {
		titleList : 'Invoice',
		listItem : [
			{ value : 'item 1'},
			{ value : 'item 2'},
			{ value : 'item 3'}
		]
	}
	let toggle = false;
	const togglelist = () => {
		toggle = !toggle;
	}
</script>

<main>
	<h1>{amountPrint}</h1>
	<button on:click={cordoba}>cordoba</button>
	<button on:click={dolares}>dolares</button>
	<button on:click={togglelist}>open invoice</button>
	<ListInvoice {...listInvoice}, open = {toggle}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	h2 {
		color: blue;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>