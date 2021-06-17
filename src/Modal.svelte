<script>
    export let showModal = false;
    export let isInfo = false;
    export let message = "Default value";
    export let header = "Default value";

</script>

<!-- If showModal is true then show it -->
{#if showModal}
    <div class="backdrop" class:info={isInfo} on:click|self>
        <div class="modal">
            <h3>{header}</h3>
            <p>{message}</p>
        </div>
    </div>
{/if}
    

<style>
    .backdrop{
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8);
    }

    .modal{
        padding: 10px;
        border-radius: 10px;
        background-color: white;
        margin: 10% auto;
        text-align: center;
        max-width: 400px;
    }

    .info .modal{
        background-color: tomato;
    }
</style>