<script lang="ts">  
    import { svelteWeb3 } from '@chiuzon/svelteweb3'
    import { onMount } from 'svelte';

    const { account, activate, error, chainId, library } = svelteWeb3()

    onMount(() => {
       
    })

</script>

{$error}
{$account}

<!-- {$error}
{$account}
{$chainId}
-->
