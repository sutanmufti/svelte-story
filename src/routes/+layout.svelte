<script lang='ts'>

    import NavigateButton from "./NavigateButton.svelte";
    import { page } from "./store";
    
    let pageCount:number;
    page.subscribe(value =>{
        pageCount = value;
    })
    function nextPage(){
        page.update(value => value + 1)
    }
    function previousPage(){
        if (pageCount > 1){
            page.update(value => value - 1)
        }
    }
</script>


<svelte:head>

    <style>
        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            height: 100vh;
        }
    </style>

</svelte:head>
{#if pageCount != 1}
<NavigateButton position='left' symbol='<' bind:page={pageCount} on:buttonClicked={previousPage}/>

{/if}
<NavigateButton position='right' bind:page={pageCount} on:buttonClicked={nextPage}/>

<div id='content'>
    <slot page={page}></slot>
</div>

<style>
    #content {
        /* border: 1px solid red; */
        height: 100%;
        display: flex;
        
    }
</style>

