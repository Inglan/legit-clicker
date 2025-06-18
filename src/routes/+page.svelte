<script lang="ts">
    let clicks = $state(0);
    let smasnugs = $state(0);

    setInterval(() => {
        clicks += smasnugs * 2;
    }, 1000);
</script>

<svelte:head>
    <title>legit clicker</title>
</svelte:head>

<div class="top-2 left-2 fixed z-10 text-white text-2xl">
    Legit Clicker - {smasnugs * 2} clicks per sec - this gmae was made in 5:29 seconds
</div>
<button
    class="w-screen h-screen flex justify-center items-center text-4xl bg-black text-white cursor-pointer"
    onclick={() => clicks++}
>
    {clicks}
</button>

<button
    class="fixed bottom-2 right-[50%] translate-x-[50%] p-3 text-black bg-white rounded cursor-pointer"
    onclick={() => {
        if (clicks >= 10) {
            smasnugs++;
            clicks -= 10;
        } else {
            alert("Not enough clicks!");
        }
    }}>Buy smasnug upgrade</button
>
