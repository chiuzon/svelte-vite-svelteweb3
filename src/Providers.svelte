<script lang="ts">
    import {ethers} from 'ethers'
    import Web3Wrapper from '@chiuzon/svelteweb3/Web3Wrapper.svelte'
    import { onMount } from 'svelte';
    import { svelteWeb3, initSvelteWeb3 } from '@chiuzon/svelteweb3'
    

    const fetchLibrary = (provider: any) => {
        const _provider = new ethers.providers.Web3Provider(provider)
        _provider.pollingInterval = 1000
        return _provider
    }

    onMount(async () => {
        //Normally you would use Web3Wrapper
        initSvelteWeb3(fetchLibrary)
    })
</script>

<!-- 
    SvelteWeb3 doesn't use react style providers, 
    but you need to have Web3Wrapper in the top level for the library to be initialized correctly 
-->
<slot />
