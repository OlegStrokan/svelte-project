<script lang="ts">
	import Nested from './Nested.svelte';
	import Profile from './Profile.svelte';
	import Posts from "./Posts.svelte";
	import AddPost from "./AddPost.svelte";

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

	export const posts = [
		{title: 'Apple changed name', id: 1},
		{title: 'Promo iphone 14 pro', id: 2},
		{title: 'Macbook 12 leaks', id: 3}
	]

	let post = {title: '', id: 4}

	const onChangePost = (newValue) => {
		post.title = newValue
	}

	const addPost = () => {
		console.log(posts)
		return posts.push(post)
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
		<Posts posts={posts}/>
		<AddPost
				posts={posts}
				onChangePost={onChangePost}
				post={post}
				addPost={addPost}

		/>
	</div>
</main>

<style>
	div {
		width: 90%;
		border: 1px solid;
		border-radius: 20px;
		padding: 20px;
		margin: 10px auto;
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

