<script>
	import ListInvoice from './ListInvoice.svelte';
	const taza = 35;
	const amount = 25
	const listInvoice = {
		titleList : 'Invoice',
		listItem : [
			{
				value : 'enacal',
				amount : 25
			},
			{
				value : 'union fenoza',
				amount : 18
			},
			{
				value : 'union fenoza',
				amount : 22
			},
			{
				value : 'enacal',
				amount : 34
			},
		]
	}
	const total = amount - (listInvoice.listItem.reduce((acc, cur) => ({amount: acc.amount + cur.amount})).amount);
	console.log(total);
	let amountPrint = `${amount} $`;
	let totalPrint = `${total} $`;
	const dolares = () => {
		amountPrint = `${amount} $`;
		totalPrint = `${total} $`;
	} 
	const cordoba = () => {
		amountPrint = `${amount * taza} c$`;
		totalPrint = `${total * taza} $`;
	}
	
	let toggle = false;
	const togglelist = () => {
		toggle = !toggle;
	}
</script>

<main>
	<h1>{amountPrint}</h1>
	<p> su balance es de {totalPrint}</p>
	<button class='btn btn-light' on:click={cordoba}>cordoba</button>
	<button class='btn btn-light' on:click={dolares}>dolares</button>
	<button class='btn btn-primary'on:click={togglelist}>open invoice</button>
	{#if toggle}
	<ListInvoice {...listInvoice}/>
	{/if}
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