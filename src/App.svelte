<script lang="ts">
	import Nested from './Nested.svelte';
	import Profile from './Profile.svelte';

	export let title = 'hello';
	export const username = 'Oleh Strokan'

	export let count = 1;

	$: doubled = count * 2;

	const changeValue = () => {
		count += 1;
	}

	export const profile12 = {
		username: 'Oleh Strokan',
		email: 'oleg14ua71@gmail.dom',
		age: 20,
		role: 'admin'
	}

</script>

<main>
	<div>
		<p>title: {title}</p>
		<p>count: {count}</p>
		<p>doubled: {doubled}</p>
		<button on:click={changeValue}>Submit</button>
	</div>
	<div>
		<Nested username={username}/>
	</div>
	<div>
		<Nested/>
	</div>
	<div>
		<Profile {...profile12}/>
	</div>
	<div>
		<Profile/>
	</div>

	<p>{title}</p>
	<p>{count}</p>
	<button on:click={changeValue}>Submit</button>
</main>

<style>
	div {
		width: 90%;
		border: 1px solid;
		border-radius: 20px;
		padding: 20px;
		margin: 20px auto;
		background-color: #b0e8e3;
	}
	button {
		padding: 15px 30px;
		background-color: #3882f8;
		border-radius: 5px;
		color: #fff;
		border: none
	}

</style>

