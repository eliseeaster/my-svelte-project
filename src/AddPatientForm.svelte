<script>

	let patients = [
		{Name: "Åge", Age: 24, Gender: "Male", id: 0},
		{Name: "Sara", Age: 29, Gender: "Female", id: 1}
	]

	let patientName;
	let age;
	let gender = 0;

	export let showForm;

	const addPatient = () => {
        
		let g = "Male";
		{if (gender==1) {
			g = "Female";
		}}
		
		let newPatient = {Name: patientName, Age: age, Gender: g, id: patients.length};
		patients[patients.length] = newPatient; 
		console.log(newPatient);
		resetFields();
        showForm = false;
        console.log(showForm)
	}

	const resetFields = () => {
		patientName = "";
		age = "";
		gender = 0;
	}

	const cancelForm = () =>{
		resetFields();
		showForm = false;
	}

</script>

<main>

	<h2>Patient List</h2>
	{#each patients as patient (patient.id)}
		<div>
			<h3>{patient.Name}</h3>
		</div>
	{/each}

	{#if showForm}
		<form on:submit|preventDefault={addPatient}>
			<input type= "text" placeholder="Name" bind:value={patientName} required/>
			<input type= "number" placeholder="Age" bind:value={age} required/>
			<label>
				<input type= "radio" bind:group={gender} value={0} required/>
				Male
			</label>
			<label>
				<input type= "radio" bind:group={gender} value={1} required/>
				Female
			</label>
			<button type="button" on:click={cancelForm}>Cancel</button>
			<button>Add patient</button>			
		</form>
		
	{/if}
	
</main>

<style>
    
</style>