<script>
  let name;
  let job;
  let age;
  let skills = [];

  const handleSubmit = () => {
    console.log(name, job, age);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name}>
  <input type="text" placeholder="job" bind:value={job}>
  <input type="number" placeholder="age" bind:value={age}>
  <label>Skills:<br>
    <input type="checkbox" bind:group={skills} value="fighting"> Fighting<br>
    <input type="checkbox" bind:group={skills} value="climbing"> Climbing<br>
    <input type="checkbox" bind:group={skills} value="swimming"> Swimming<br>
  </label>
  <button>Add person</button>
</form>

<style>

</style>
