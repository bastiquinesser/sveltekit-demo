<script>
	import { supabase } from '$lib/supabase';
	import { onMount } from 'svelte';

	let transactionList = [':)'];

	async function getTransactions() {
		let { data: transactions, error } = await supabase.from('transaction').select('*');
		transactionList = transactions;
	}

	onMount(() => {
		getTransactions();
	});
</script>

<div>{JSON.stringify(transactionList)}</div>
