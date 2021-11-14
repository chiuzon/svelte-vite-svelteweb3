<script lang='ts'>
	import './styles/mini-default.min.css'

	import Providers from './Providers.svelte'
	import ConnectedView from './views/ConnectedView.svelte'
	import UnconnectedView from './views/UnconnectedView.svelte'

	import { svelteWeb3 } from '@chiuzon/svelteweb3'

	const { account } = svelteWeb3()
</script>

<Providers>
	<div class="container responsive-margin responsive-padding">
	<!-- We store the account address in a derived store so you need to access it using the $ prefix -->
	{#if $account}
		<ConnectedView />
	{:else}
		<UnconnectedView />
	{/if}
	</div>

	<a href="https://github.com/chiuzon/svelteWeb3">svelteWeb3 Library</a>
</Providers>	

<style>
	.container {
		display: flex;
		justify-content: center;
	}
</style>