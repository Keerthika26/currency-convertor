<template>
    <div class="currency">
        <h2> Currency Convertor </h2>
        <div class="f">
            <label> Enter the Amount: &nbsp; </label>
            <input type="text" v-model="currency" />
        </div>
        <div class="currency-convertor">
            <div class="f">
                <label> Convert From: &nbsp; </label>
                <select v-model="selectedCurrencyFrom">
                    <option v-for="option, i in options" :key="i"> {{ option.name }} </option>
                </select>
            </div>
            <div class="f">
                <label> Convert To: &nbsp; </label>
                <select v-model="selectedCurrencyTo">
                    <option v-for="option, j in options" :key="j"> {{ option.name }} </option>
                </select>
            </div>
        </div>
        <p> {{ currency }} {{ selectedCurrencyFrom }} equals to {{ convert(selectedCurrencyFrom, selectedCurrencyTo, currency)}} {{ selectedCurrencyTo}} </p>
    </div>
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
	padding: 1rem
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