<script>
    // EVENT MODIFIERS 
    // 1 - Once - makes sure event can only be fired once (removes event handler)
    // 2 - Prevent Default - prevent the default action (run e.preventDefault())
    // 3 - self - only fires event if the clicked element is the target



    export let message = "default value";
    // export show modal to app so can be toggled outside of modal
    export let showModal = false;
    export let isPromo = false;
</script>

{#if showModal}
<!-- add conditional styling using class:x={} -->
<!-- use single pipe to add event modifier -->
<div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
        <p>{message}</p>
    </div>
</div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }

    .modal {
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background: white;
    }

    .promo .modal {
        background: crimson;
        color: white;
    }
</style>