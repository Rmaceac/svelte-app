<script>
  let name;
  let job;
  let age;
  let fighting = false;
  let climbing = false;
  let swimming = false;

  const handleSubmit = () => {
    console.log(name, job, age);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name}>
  <input type="text" placeholder="job" bind:value={job}>
  <input type="number" placeholder="age" bind:value={age}>
  <label>Skills:<br>
    <input type="checkbox" bind:checked={fighting}> Fighting<br>
    <input type="checkbox" bind:checked={climbing}> Climbing<br>
    <input type="checkbox" bind:checked={swimming}> Swimming<br>
  </label>
  <button>Add person</button>
</form>

<style>

</style>
