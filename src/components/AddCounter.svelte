<script lang="ts">
    import { createEventDispatcher } from 'svelte'

const dispatch = createEventDispatcher();

function addNewCounter(e:any){
    e.preventDefault();
    dispatch("addcounter");
}

</script>

<main>
    <button class="add" on:click={addNewCounter}>new counter</button>
</main>

<style>
    .add{
        width: 400px;
        color: white;
        background-color: #68d391;
        border-radius: 7px;
        padding-top: 5px;
        padding-bottom: 5px;
    }
</style>