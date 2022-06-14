<template>
	<!-- choice coin logo goes here -->
	<img alt="Vue logo" src="./assets/logo.png" />

	<div class="container">
		<div class="final-result">
			<p>
				compliance score result: <span>{{ userdata }} </span>
			</p>
		</div>

		<div class="data">
			<h3>Equity: {{ equity }}</h3>
			<select v-model="equity">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>Decentralization: {{ decentralization }}</h3>
			<select v-model="decentralization">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>participation: {{ participation }}</h3>
			<select v-model="participation">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>investment: {{ investment }}</h3>
			<select v-model="investment">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>utility: {{ utility }}</h3>
			<select v-model="utility">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>purpose: {{ purpose }}</h3>
			<select v-model="purpose">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>control: {{ control }}</h3>
			<select v-model="control">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<div class="data">
			<h3>derivatives: {{ derivatives }}</h3>
			<select v-model="derivatives">
				<option disabled value="">Please select 1 option</option>
				<option
					v-for="detail in details"
					:key="detail"
					v-bind:value="detail.score"
				>
					{{ detail.values }}
				</option>
			</select>
		</div>

		<button @click="calculate">calculate compliance score</button>
	</div>
</template>

<script>
	export default {
		name: "App",
		data() {
			return {
				details: [
					{
						values: "good",
						score: 0.75,
					},
					{
						values: "acceptable",
						score: 0.5,
					},
					{
						values: "outstanding",
						score: 1,
					},
					{
						values: "unacceptable",
						score: 0,
					},
					{
						values: "marginal",
						score: 0.25,
					},
				],
				userdata: null,
				userdata2: null,
				equity: null,
				decentralization: null,
				participation: null,
				investment: null,
				utility: null,
				purpose: null,
				control: null,
				derivatives: null,
			};
		},
		methods: {
			calculate() {
				const result =
					this.equity *
					this.decentralization *
					this.participation *
					this.investment *
					this.utility *
					this.purpose *
					this.control *
					this.derivatives;

				this.userdata = result;
				this.userdata2 = result ** (1 / 9);

				console.log("Final result: ", this.userdata2);
				console.log(this.equity);
				console.log(this.decentralization);
				console.log(this.participation);
				console.log(this.investment);
				console.log(this.utility);
				console.log(this.purpose);
				console.log(this.control);
				console.log(this.derivatives);
			},
		},
	};
</script>

<style>
	span {
		border: 1px solid;
		padding: 5px;
	}
	img {
		margin-left: 50%;
		height: 60px;
		text-align: center;
	}
	.container {
		border-radius: 5px;
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		color: #2c3e50;
		width: 600px;
		background-color: rgba(33, 90, 141, 0.311);
		box-shadow: 0 1px 0 1px rgba(128, 128, 128, 0.401);
		position: absolute;
		left: 35%;
	}

	.data {
		margin-bottom: 3px;
		border-radius: 5px;
		width: 300px;
		height: 90px;
		margin-right: 100px;
	}

	.data h3 {
		letter-spacing: 2px;
		font-weight: bold;
		font-size: 15px;
		text-transform: uppercase;
	}
	select {
		border-radius: 5px;
		width: 400px;
		background-color: gainsboro;
		padding: 5px;
	}

	button {
		background-color: gainsboro;
		border: 1px solid;
		border-radius: 5px;
		padding: 5px;
		margin-bottom: 10px;
		margin-top: 10px;
		letter-spacing: 2px;
		font-weight: 700;
		text-transform: uppercase;
		height: 50px;
		width: 400px;
		cursor: pointer;
	}

	.final-result {
		width: 100%;
		border: 1px dashed gray;
	}

	.final-result p {
		text-transform: capitalize;
		padding: 5px;
		font-size: 16px;
		letter-spacing: 2px;
		font-weight: bolder;
		margin-left: 70px;
	}
</style>
