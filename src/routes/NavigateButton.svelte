<script lang='ts'>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher()
    export let position = 'left';
    export let symbol = '>'
    export let page: number;
    let style='left: 0';
    
    $: if (position == 'left') {
        style='left: 0';
    } else if (position=='right'){
        style='right: 0';
    }

    function buttonClicked(){
        dispatch('buttonClicked')
    }
</script>


<div id='leftButton' style={style} on:click={buttonClicked} on:keydown={buttonClicked}>
    <h1>{symbol}{page}</h1>
</div>


<style>
    #leftButton {
        display: flex  ;
        position: fixed;
        top: 0;
        /* left: 0; */
        height: 100%;
        /* border: 1px solid blue; */
        justify-content: center;
        align-items: center;
        background-color: rgb(0,0,0,0.1);
        cursor: pointer;
        
    }
</style>