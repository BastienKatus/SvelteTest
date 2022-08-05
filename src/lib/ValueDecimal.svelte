<script>
    export let value;
    export let min;
    export let max;
    export let precision;

    const handleChange = (e) => {
        if ( e != null && e != undefined &&
             e.target != null && e.target != undefined &&
             !isNaN(e.target.value) ){
                
            // TODO
            value = e.target.value;
            if(value != ""){
                /* Gestion min et max */
                if(value > max){
                    value = max;
                }
                else if(value < min){
                    value = min;
                }

                /* Gestion précision */
                let valueComposition = String(value).split('.');
                if(valueComposition && valueComposition[1]){
                    let handlePrecision = String(valueComposition[1]).length;
                    if(handlePrecision > precision){
                        value = valueComposition[0] + '.' + valueComposition[1].slice(0,precision);
                    }
                }
            }
            // -------------------------
        }
    }
</script>
<div class="tooltip tooltip-right" data-tip= "Max: {max ?? 'none'} |  Min: {min ?? 'none'} | Precision: {precision ?? 'none'}">
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
