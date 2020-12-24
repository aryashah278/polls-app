<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Tabs from './shared/Tabs.svelte';

	const items = ['Current Polls','Add a new poll'];
	let activeItem = 'Current Polls';

	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange} />
	{#if activeItem === 'Current Polls'}
		<p>Current polls components go here</p>
	{:else if activeItem === 'Add a new poll'}
		<p>Add new poll form goes here</p>
	{/if}
</main>
<Footer /> 

<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>