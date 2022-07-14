<script>
	let firstname = 'Archana';
	let lastname = 'hegde';
	$:name = `${firstname} ${lastname}`;
	let beltColour = 'black';
	$: console.log(beltColour)

	let showmodal = false;

	const clickHandle = () =>{
		beltColour ='red';
	}

	const handleInput =(e) =>{
		beltColour = e.target.value
	}

	const toggleModal = () => {
		showmodal = !showmodal;
	}
	import ForLoopExample from "./ForLoopExample.svelte";
	import Modal from "./Modal.svelte"
	import AddPersonForm from "./AddPersonForm.svelte";
</script>

<Modal isPromo={false} {showmodal} on:click={toggleModal}> 
	<AddPersonForm/>
	<div slot="title">
		<h3>Add a new Person</h3>
	</div>
</Modal>
<ForLoopExample/>
<main>
<!--	<p style="color:{beltColour}"> {name} {beltColour} belt</p>
	<button on:click={clickHandle}>Update Colour</button>
	<input type="text" bind:value={firstname}>
	<input type="text" bind:value={lastname}>
	<input type="text" bind:value = {beltColour}> --> <!-- two way data binding -->


	<button on:click={toggleModal}>OpenModal</button> <!-- on:click|once={toggleModal} only once event is fired-->
</main>
	<!-- <ForLoopExample/> -->
<style>
	main{
		text-align: center;
		padding: auto;
		max-width: 240px;
		margin: 0 auto;
	}
	@media (min-width: 640px){
		main{
			max-width: none;
		}
	}
	h1{
		color: orange;
		text-transform: uppercase;
		font-size: 4em;
	}
</style>