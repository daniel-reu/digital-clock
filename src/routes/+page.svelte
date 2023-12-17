<script>
	import { onMount } from "svelte";


    let date = getNewDate();

    function getNewDate() {
        return new Date().toLocaleString().split(", ")[1];
    }

    onMount(() => {
        const interval = setInterval(() => {
            date = getNewDate();
        }, 1000);

        return () => {
            clearInterval(interval);            
        }
    });

</script>

<div class="flex flex-col justify-center w-full items-center min-h-screen">
    <div class="mb-5">
        <span class="text-[55px]">Current time</span>
    </div>
    <div>
        <span class="text-[45px]">{date}</span>
    </div>
</div>

<style lang="postcss">
    :global(html) {
        background-color: #8697d1;
    }
</style>