<script lang="ts">  
    import { svelteWeb3 } from '@chiuzon/svelteweb3'
    import { onMount } from 'svelte';

    const { account, chainId } = svelteWeb3()

    onMount(() => {
       
    })

</script>


<p>Account : {$account}</p>
<p>ChainId : {$chainId}</p>
