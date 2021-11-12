<script lang="ts">
    import { WalletConnectConnector } from '@web3-react/walletconnect-connector'
    
    import { svelteWeb3 } from '@chiuzon/svelteweb3'
import { onMount } from 'svelte';

    const { account, activate, error, chainId, library } = svelteWeb3()

    let walletconnect = new WalletConnectConnector({
            rpc: { 1: "https://mainnet.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161" },
            qrcode: true
    })

    onMount(() => {
        (window as any)['global'] = window
    })

    const login = async () => {
       await activate(walletconnect, async (error) => {
           console.log(error)
       })
    }
</script>

<h1>Hello World</h1>

{$error}
{$account}

<!-- {$error}
{$account}
{$chainId}
-->

<button on:click={login}>
    Connect
</button>