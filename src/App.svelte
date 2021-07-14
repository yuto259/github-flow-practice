<script lang="ts">
import AddCounter from './components/AddCounter.svelte'
import Counter from './components/Counter.svelte'

$: counters = [
	{
		name:'new',
		value: 0,
		id: 0
	}
];
$: list = counters.map((counter)=>counter.name).join(',');
$: gokei = counters.length ? counters.map(item => item.value).reduce((prev, next) => prev + next) : 0;
$: newid = counters.length ? Math.max(...(counters.map((c)=>c.id))) + 1 : 0;
;
const addCounter = (e:any) => {

	const newCounter = {
		name: 'new' ,
		value: 0,
		id: newid
	}
	counters = [...counters, newCounter];
}

const removeCounter = (e:any) => {
	counters = counters.filter((counter)=> counter.id !== e.detail)
}

  </script>
  
<main>
	<h1 style="font-size: 70px;display: block;">Multiple Counter</h1>
	<div class="new">
		
			{#if counters.length === 0}
			<p></p>
			{:else}
			{#each counters as counter }
				<Counter 
				bind:name={counter.name}
				bind:value={counter.value}
				id={counter.id}
				on:removecounter={removeCounter}/>
			{/each}
			{/if}
			<div>
				<AddCounter on:addcounter={addCounter} />
			</div>
			<div class="info"><span>title list:{list}</span></div>
			<div class="info"><span>sum of count:{gokei}</span></div>
			
		</div>
</main>
  
<style>
	  main {
		  width: 100%;
		  text-align: center;
		  padding:10px;
		  margin:0px
	  }

	  .new {
		  width: 400px;
		  margin-left: auto;
		  margin-right: auto;
	  }

	  .info{
	    display: block;
		margin:10px;
		text-align: center;
		font-size:14px;
	}

</style>

