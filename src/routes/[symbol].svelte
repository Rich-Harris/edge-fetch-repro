<script context="module">
	export async function load({ params, fetch }) {
		const res = await fetch(`https://api.stockanalysis.com/wp-json/sa/info?s=${params.symbol}&t=stocks`)

		return {
			props: {
				text: await res.text()
			}
		}
	}
</script>

<script>
	export let text
</script>

<div>{text}</div>
