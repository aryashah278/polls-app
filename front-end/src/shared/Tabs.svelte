<script>
    
    import {createEventDispatcher} from 'svelte';

    const dispatcher = createEventDispatcher();

    export let items;
    export let activeItem;

</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <li on:click={() => dispatcher('tabChange', item)}>
                <div class:active={item === activeItem}>{item}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs{
        margin-bottom: 40px;
    }
    ul{
        list-style-type: none;
        display: flex;
        justify-content: center;
        padding: 0px;
    }
    li{
        font-size: 18px;
        margin: 0 16px;
        color: grey; 
        cursor: pointer;
    }
    .active{
        color: red;
        border-bottom: 2px solid red;
        padding-bottom: 8px;
    }
</style>