<script>
  import { createEventDispatcher } from "svelte";
  let dispatch = createEventDispatcher();

  let name;
  let job;
  let age;
  let jobs = ["ninja", "blacksmith", "cobbler", "baker"];
  let chosenJob;
  let skills = [];

  const handleSubmit = () => {
    const person = {
      name : name,
      job: chosenJob,
      age: age,
      skills: skills,
    }
    dispatch("addPerson", person);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name}>
  <input type="number" placeholder="age" bind:value={age}>
  <label>
    <select bind:value={chosenJob}>
      {#each jobs as job}
        <option value={job}>{job}</option>
      {/each}
    </select>
  </label>
  <label>Skills:<br>
    <input type="checkbox" bind:group={skills} value="fighting"> Fighting<br>
    <input type="checkbox" bind:group={skills} value="climbing"> Climbing<br>
    <input type="checkbox" bind:group={skills} value="swimming"> Swimming<br>
  </label>
  <button>Add person</button>
</form>

<style>

</style>
