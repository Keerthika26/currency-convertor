<template lang="pug">
.currency
	h2 Currency Convertor
	.f
		label Enter the Amount: &nbsp;
		input(type="text", v-model="currency")
	.currency-convertor
		.f
			label Convert From: &nbsp;
			select(v-model="selectedCurrencyFrom")
				option(v-for="option, i in options") {{ option.name }}
		.f
			label Convert To: &nbsp;
			select(v-model="selectedCurrencyTo")
				option(v-for="option, i in options") {{ option.name }}
	p {{ currency }} {{ selectedCurrencyFrom }} equals to {{ convert(selectedCurrencyFrom, selectedCurrencyTo, currency)}} {{ selectedCurrencyTo}}
</template>

<script>
export default {
	data() {
		return {
			currency: '',
			selectedCurrencyFrom: 'Indian Rupees',
			selectedCurrencyTo: 'Baharaini Dinar',
			options: [
				{
					name: 'Indian Rupees',
					currencyName: 'INR'
				},
				{
					name: 'US Dollars',
					currencyName: 'USD'
				},
				{
					name: 'Euro',
					currencyName: 'EU'
				},
				{
					name: 'Baharaini Dinar',
					currencyName: 'BHD'
				}
			]
		}
	},
	methods: {
		convert(from, to, currency) {
			if (from === 'Indian Rupees' && to === 'Baharaini Dinar') {
				return currency * 0.0059
			}
		}
	}
}
</script>

<style lang="sass" scoped>

.currency
	padding: 2rem
	width: 50rem
	.f
		display: block
		margin: 1rem 0
	.currency-convertor
		display: flex
		.f
			&:first-child
				margin-right: 1rem !important
</style>