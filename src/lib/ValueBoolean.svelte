<script>
    export let value;
    export let desc;
</script>

<style>
    .flex_column{
        display: flex;
        flex-direction: column;
        border: 1px solid blueviolet;
        padding: 15px;
    }
    span{
        margin-right: auto;
        margin-bottom: 15px;
    }
</style>

<div class="tooltip tooltip-right flex_column">
    <span>
        {#if desc}
            {desc}
        {/if}
    </span>
    <input
        type="checkbox"
        bind:checked = {value}
        class="toggle toggle-accent"
    />
</div>