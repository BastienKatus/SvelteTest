<script>
    export let value;
    export let min;
    export let max;

    const handleChange = (e) => {
        if ( e != null && e != undefined &&
             e.target != null && e.target != undefined &&
             !isNaN(e.target.value) ){

            // TODO
            value = e.target.value;
            if(value != ""){
                if(value > max){
                    value = max;
                }
                else if(value < min){
                    value = min;
                }
            }
            // -------------------------
        }
    }
 
</script>

<div class="tooltip tooltip-right" data-tip= "Max: {max ?? 'none'} |  Min: {min ?? 'none'} ">
<input
        type="number"
        step="1"
        min="{min ?? ''}"
        max="{max ?? ''}"
        bind:value ="{value}"
        class="input input-bordered w-full border-accent"
        on:change ="{handleChange}"
/>
</div>