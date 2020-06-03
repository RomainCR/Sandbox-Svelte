<script>
import Modal from './Modal.svelte'
import AddPersonForm from './AddPersonForm.svelte'
let people =
  [
		{
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
      "street": "Kulas Light",
      "suite": "Apt. 556",
      "city": "Gwenborough",
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  },
  {
    "id": 2,
    "name": "Ervin Howell",
    "username": "Antonette",
    "email": "Shanna@melissa.tv",
    "address": {
      "street": "Victor Plains",
      "suite": "Suite 879",
      "city": "Wisokyburgh",
      "zipcode": "90566-7771",
      "geo": {
        "lat": "-43.9509",
        "lng": "-34.4618"
      }
    },
    "phone": "010-692-6593 x09125",
    "website": "anastasia.net",
    "company": {
      "name": "Deckow-Crist",
      "catchPhrase": "Proactive didactic contingency",
      "bs": "synergize scalable supply-chains"
    }
	},
	  {
    "id": 3,
    "name": "Clementine Bauch",
    "username": "Samantha",
    "email": "Nathan@yesenia.net",
    "address": {
      "street": "Douglas Extension",
      "suite": "Suite 847",
      "city": "McKenziehaven",
      "zipcode": "59590-4157",
      "geo": {
        "lat": "-68.6102",
        "lng": "-47.0653"
      }
    },
    "phone": "1-463-123-4447",
    "website": "ramiro.info",
    "company": {
      "name": "Romaguera-Jacobson",
      "catchPhrase": "Face to face bifurcated interface",
      "bs": "e-enable strategic applications"
    }
  }
	]
	let firstName = "Le roi";
	let lastName = "Boufs";
	let color = "black";
	let n = 0
	let showModal = false;
	const deletePerson = (id) => {
		people = people.filter(person => person.id !== id)
	}
	const toggleModal = () => {
		showModal = !showModal
	}
	$:fullName = `${firstName} des ${lastName}`
	$: {
		showModal
		console.log("showModal", showModal);
	}
</script>
<!--  
<Modal message="HELLO" {showModal} on:click={toggleModal} />
-->
<Modal {showModal} on:click={toggleModal}>
  <AddPersonForm />
</Modal>

<main>
	<h1 style="color: {color}">Hello {fullName}!</h1>
  <button on:click={toggleModal}>TOUCH</button>
	<input type="text" placeholder="firstName" bind:value={firstName}>
	<input type="text" placeholder="lastName" bind:value={lastName}>
	<select name="colors" id="colors" bind:value={color}>
		<option value="black">BLACK</option>
		<option value="red">RED</option>
		<option value="green">GREEN</option>
		<option value="blue">BLUE</option>
	</select>

	{#each people as person (person.id)}
		<div>{person.name} : {person.username} <button on:click={deletePerson(person.id)}>X</button></div>
		{:else}
		<p>Nothing to show</p>
	{/each}
</main>

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