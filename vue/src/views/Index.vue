<template>
	<div>
		<div class="container">
			{{staking}}<br>
			{{address}}
			<SpWelcome />
			<SpTokenSend :address="address" />
			<SpTransferList :address="address" />
		</div>
	</div>
</template>

<script>
export default {
	name: 'Index',
	data() {
		return {
			stake: null,
		}
	},
	computed: {
		address() {
			return this.$store.getters['common/wallet/address']
		}
	},
	mounted() {
		this.staking = this.$store.getters['cosmos.staking.v1beta1/getParams']()
	}
}
</script>
