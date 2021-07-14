<script lang="ts">
    import { createEventDispatcher } from "svelte/internal";

export let name:string;
export let value:number;
export let id:number;

const dispatch = createEventDispatcher();

const addPoint = () => { if(value < 100) { value+=1;}}
const removePoint = () => {if (value > 0){ value-=1;}}
const resetPoint = () => (value = 0);
const deleteCounter = () => {
    dispatch("removecounter",id);
};

</script>

<main>
    <div class="card">
        <input type="text" style="background-color: white; color:rgb(177, 171, 171);;"placeholder="new" bind:value={name}/>
        <h2>{value}</h2>
        <button style="padding: 8px 10px;color: white;background-color: #fa8072;border-radius: 5px 0 0 5px;" class="button" on:click={addPoint}>+</button>
        <button style="padding: 8px 10px;color: white;background-color: #00bfff;" class="button" on:click={removePoint}>-</button>
        <button style="padding: 8px 10px;color: white;background-color: #f0e68c;border-radius: 0 5px 5px 0;" class="button" on:click={resetPoint}>0</button>
        <button style="border: none;outline: none;background: transparent;color: rgb(177, 171, 171);font-size: 20px;margin-left:40px;" on:click={deleteCounter}>×</button>
    </div>
</main>

<style>
    h2{
    margin-right: 5%;
    margin-left: 5%;
    width: 10%;
}
    .button{
        margin-top: 3px;
        margin-bottom: 3px;
        display:flex;
        align-items: center;
        justify-content: center;
    }

    .card {
    display:flex;
    flex-direction:row;
    align-items: center;
    justify-content: center;
    background-color:#f5f5f5;
    box-shadow: 0 10px 15px -3px rgb(0 0 0 / 10%), 0 4px 6px -2px rgb(0 0 0 / 5%);
	border-radius: 7px;
    margin-right: auto;
    margin-left: auto;
    margin-top: 10px;
    margin-bottom: 10px;
}
input{
    width: 30%;
}
@media(min-width:640px){
    main{
        max-width:none ;
    }
}
    



    
</style>