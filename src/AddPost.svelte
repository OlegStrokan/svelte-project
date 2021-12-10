<script>
    export let posts
    export let addPost
    export let post
    export let onChangePost

</script>


<p>Add Post</p>
<input type="text" value={post.title} on:change={(e) => onChangePost(e.target.value)}>
<button on:click={addPost}>Submit</button>

