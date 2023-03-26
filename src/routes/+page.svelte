
<script lang='ts'>
    import { page } from "./store";
    import Page1 from "../Components/Page1.svelte";
    import Page2 from "../Components/Page2.svelte";
    import Page3 from "../Components/Page3.svelte";
    let pageCount: number ;
    page.subscribe(value=>{
        pageCount=value;
    })
    
</script>

<div>
    {#if pageCount == 1}
    <Page1/>
    {/if }
    {#if pageCount == 2}
    <Page2/>
    {/if }
    {#if pageCount == 3}
    <Page3/>
    {/if }
    
</div>
