<script>
  let name;
  let color;
  let age;
  let skills = []
  $: {
		age
		console.log("type of age", age, typeof(age));
	}
  const handleSubmit = () => {
    console.log(name, color, age, skills);   
  }
</script>

  <form on:submit|preventDefault={handleSubmit} >
      <input type="text" placeholder="name" bind:value={name}>
      <input type="text" placeholder="color" bind:value={color}>
      <input type="number" placeholder="age" bind:value={age}>
      <select name="colors" id="colors" bind:value={color}>
      <option value="black">BLACK</option>
      <option value="red">RED</option>
      <option value="green">GREEN</option>
      <option value="blue">BLUE</option>
	    </select>
        <label>SKILLS</label>
        <input type="checkbox" bind:group={skills} value="fighting">fighting
        <input type="checkbox" bind:group={skills} value="running">running
        <input type="checkbox" bind:group={skills} value="cheating">cheating
      <button>ADD PERSON</button>
    </form>
<style>

</style>