<script>
    export let showmodal = false;
    export let isPromo =false
</script>

{#if showmodal}
<div class="backdrop" class:promo={isPromo} on:click|self> <!-- self -->
    <div class="modal">
        <slot name="title"></slot>
        <slot></slot>
    </div>
</div>
{/if}

<style>
    .backdrop{
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }
    .modal{
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        text-align: center ;
        margin:10% auto;
        background: white;
    }
    .promo .modal{
        background: red;
        color: white;
    }
</style>