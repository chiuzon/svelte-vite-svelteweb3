<script lang="ts">
    import { svelteWeb3 } from '@chiuzon/svelteweb3'
    import { InjectedConnector } from '@web3-react/injected-connector'

    const { activate, error } = svelteWeb3()

    const injectedConnector = new InjectedConnector({
        //You can specify what chains you want to support
        supportedChainIds: [3]
    })

    const onConnectButton = async () => {
        await activate(injectedConnector, async (e) => {
            //You can ask here the user if he wanna switch networks or show a popup modal
            console.error(e)
        })
    }
</script>

<div class="connect-box">
    {$error ?? 'Please use Ropsten Network'}

    <button on:click={onConnectButton}>
        Connect
    </button>
</div>

<style>
    .connect-box {
        display: flex;
        flex-direction: column;
    }
</style>