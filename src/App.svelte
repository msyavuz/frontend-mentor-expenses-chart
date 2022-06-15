<script>
	import data from "../assets/data";

	let total = 0;
	for (let day of data) {
		total += day.amount;
	}
	console.log(data[0].amount);
</script>

<div class="outer card">
	<div class="upper card">
		<h2 class="balance container">
			My balance <h2>$921.48</h2>
		</h2>
		<img src="../assets/images/logo.svg" alt="logo" id="logo" />
	</div>
	<div class="lower card">
		<h1>Spending - Last 7 Days</h1>
		<div class="graph">
			{#each data as day}
				<div class="column-container">
					<div class="spending" style="height:{Math.floor(day.amount)}%" />
					<div class="spending-context">{day.amount}</div>
				</div>
			{/each}
		</div>
		<hr />
		<div class="summary">
			<div class="total">
				<p>Total this month</p>
				<h1>${total}</h1>
			</div>
			<div class="percentage">
				<b>%2.4</b>
				<p>from last month</p>
			</div>
		</div>
	</div>
</div>

<style>
	@import url("https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@1,700&display=swap");
	.card {
		border-radius: 20px;
		font-family: "DM Sans", sans-serif;
		font-size: 18px;
	}
	.outer {
		height: 80vh;
		width: 30vw;
		display: grid;
		grid-template-rows: 1fr 2fr;
		gap: 2em;
		justify-content: center;
	}
	.upper {
		display: grid;
		grid-template-columns: 3fr 1fr;
		justify-content: center;
		align-items: center;
		background-color: orange;
		color: white;
		padding-left: 2em;
	}
	.lower {
		background-color: hsl(33, 100%, 98%);
		padding: 2em;
		display: flex;
		flex-direction: column;
		justify-content: baseline;
		gap: 2em;
	}
	.summary {
		display: grid;
		grid-template-columns: 2fr 1fr;
		justify-content: center;
		align-items: center;
	}
	p {
		color: gray;
	}
	.graph {
		display: flex;
		justify-content: space-between;
		gap: 2em;
		height: 50%;
	}

	hr {
		width: 100%;
	}
	.column-container {
		display: flex;
		flex-direction: column;
		align-items: baseline;
		justify-content: baseline;
		gap: 10px;
	}

	.spending {
		width: 50px;
		background-color: orange;
		align-self: center;
		justify-self: flex-end;
		padding: 10px 0;
		display: flex;
		justify-content: center;
		align-items: center;
		overflow: hidden;
	}
	.spending:active,
	.spending:hover {
		background-color: hsl(186, 34%, 60%);
	}
	.spending-context {
		display: none;
		justify-items: center;
		align-items: center;
		width: 100%;
		background-color: hsl(25, 47%, 15%);
		color: white;
		padding: 1px 10%;
		border-radius: 5px;
		overflow: hidden;
		margin: 0 0;
	}
	.column-container:hover .spending-context {
		display: flex;
	}
	h1 {
		font-size: x-large;
	}
	h2 {
		font-size: larger;
	}
</style>
