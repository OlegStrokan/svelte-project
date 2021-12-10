<script>
    import Post from "./Post.svelte";

    export let posts
    $: posts
</script>


<p>Posts</p>
{#each posts as {title}, i}
    <Post title={title} postId={i}/>
{/each}
