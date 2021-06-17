

<script>
import Modal from './Modal.svelte'
let showModal = false;

const toggleModal = () => {
	showModal = !showModal;
}

</script>

<Modal header="Information" message="Here is some information" isInfo={true} {showModal} on:click={toggleModal}/>
<main>
	<button on:click={toggleModal}>Open modal</button>
</main>

<style>

	main{
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media(min-width: 640px){
		main{
			max-width: none;
		}
	}

</style>