<script>
import Contactcard from './Contactcard.svelte';
  export let name;
  export let age;
console.log(age);
$:uppercaseName=name.toUpperCase();
$:console.log(name);
$:if(name=='Maximo Decimo'){
	age=100;
}

	function incrementAge() {
    age += 1;
	};
	function changeName(){
		name="Maximo Decimo"
	};
	function nameInput(event){
		const enterValue=event.target.value;
		name=enterValue;
	}
</script>
<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
<main>
  <h3>Hello {uppercaseName}, and my age is {age}</h3>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <button on:click={incrementAge}>increment</button>
	<!-- <button on:click={changeName}>Change Name</button> -->
	<br>
	<!-- <input type="text" value={name} on:input={nameInput}> -->
	<input type="text" bind:value={name}/>


<Contactcard userName={name}/>


</main>
