
<script lang='ts'>
    import { page } from "./store";
    let pageCount: number ;
    page.subscribe(value=>{
        pageCount=value;
    })
    
</script>

<div>
    <h1>Welcome to SvelteKit {pageCount}</h1>
    <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

</div>
