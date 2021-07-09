<script>

let list = [i]
i = 0;

let count = 0;

function addItem(){
	list = [...list,0]
}

function countUp(){
	list[i] = list[i]++;
}

function countDown(){
	if(count >= 1){
	  count--;
	}
}

function countReset(){
	count = 0;
}

function delete1(){
	// 要素の削除
	const div1 = document.getElementById("countboxs");
	if (div1.hasChildNodes()){
		div1.removeChild(div1.firstChild);
	}
}


  </script>
  
<main>
	<h1>Multiple Counter</h1>
	<div class="main">
		<div class="countboxs" id="countboxs">
			{#each list as _item}
	    <div class="countbox" id="countbox">
	    	<div class="text">
		        <input value="new">
	        </div>
		    <div class="count" id=count>{count}</div>
		    <div class=button>
			    <button class="buttonred" on:click={countUp}>+</button>
				<button class="buttonblue" on:click={countDown}>-</button>
				<button class="buttonyellow" on:click={countReset}>0</button>
		    </div>
			<button class=deletebutton on:click={delete1}>×</button>
	    </div>
		{/each}
    	</div>
	    <div class="newcounter">
		    <button class="addbutton" on:click={addItem}>new counter</button>
	    </div>
		<div class="sum">
		    <span>sum of count:</span>
	    </div>
    </div>
</main>
  
<style>
	  main {
		  width: 100%;
	  }

	  .main {
		  width: 400px;
		  margin-left: auto;
		  margin-right: auto;
	  }

	  h1 {
		  font-size: 70px;
		  text-align: center;
	  }

	  .countbox {
		  margin-top: 10px;
		  display: flex;
		  background-color: #f5f5f5;
		  box-shadow: 0 10px 15px -3px rgb(0 0 0 / 10%), 0 4px 6px -2px rgb(0 0 0 / 5%);
		  border-radius: 7px;
	  }

	  .text input {
		  color: rgb(177, 171, 171);
		  margin-top: 8px;
		  margin-left: 8px;
		  padding-top: 2px;
		  padding-bottom: 2px;
	  }

	  .count {
		  margin:8px 20px 5px 20px;
	  }

	  .button {
		margin-top: 3px;
		margin-bottom: 3px;
	  }

	  .buttonred {
		  padding: 8px 10px;
		  color: white;
		  background-color: #fa8072;
		  border-radius: 5px 0 0 5px;
	  }

	  .buttonblue {
		  margin-left: -4px;
		  margin-right: -4px;
		  padding: 8px 10px;
		  color: white;
		  background-color: #00bfff;
	  }

	  .buttonyellow {
	      padding: 8px 10px;
		  color: white;
		  background-color: #f0e68c;
		  border-radius: 0 5px 5px 0;
	  }

	  .newcounter {
		  text-align: center;
	  }

	  .newcounter button {
		  width: 400px;
		  margin-top: 10px;
		  padding: 5px 0 5px 0;
		  background-color: #7bd37b;
		  color:white;
		  border-radius: 8px;
	  }

	  .deletebutton {
		  border: none;  /* 枠線を消す */
          outline: none; /* クリックしたときに表示される枠線を消す */
          background: transparent; /* 背景の灰色を消す */
		  color: rgb(177, 171, 171);
		  font-size: 20px;
		  margin-left:40px;
	  }

	  .sum {
		  text-align: center;
		  margin-top: 5px;
	  }

</style>

