<script>
    import {Setting} from '$lib';
    export let settings;
</script>

<h1 class="prose text-4xl text-center my-10">Type: Time</h1>

<div class="mx-10 form-control">
    {#if settings}
        {#each Object.entries(settings) as [category, setting]}
            {#if settings.dailyReset && settings.dailyReset.desc}
                <p class="italic">{settings.dailyReset.desc}</p>  
            {/if}    
            <Setting setting="{setting}" category="{category}" level={0} />
        {/each}
    {/if}
</div>


