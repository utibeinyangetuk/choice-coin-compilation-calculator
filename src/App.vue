<template>
	<!-- choice coin logo goes here -->
	<img alt="Vue logo" src="./assets/logo.png" />
	<h3>{{userdata}}</h3>

	<div class="container">
		<div class="data">
			<h3>Equity : {{ equity }}</h3>
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
			<h3>Decentralization : {{ decentralization }}</h3>
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
			<h3>participation : {{ participation }}</h3>
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
			<h3>investment : {{ investment }}</h3>
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
			<h3>utility : {{ utility }}</h3>
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
			<h3>purpose : {{ purpose }}</h3>
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
			<h3>control : {{ control }}</h3>
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
			<h3>derivatives : {{ derivatives }}</h3>
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
				userdata:'',
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
			const	result =
					this.equity *
					this.decentralization *
					this.participation *
					this.investment *
					this.utility *
					this.purpose *
					this.control *
					this.derivatives;

					this.userdata=result
			},
		},
	};
</script>

<style>
	img {
		height: 60px;
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
		box-shadow: 0 2px 2px #999;
		position: absolute;
		left: 35%;
	}

	.data {
		margin-bottom: 10px;
		border-radius: 5px;
		width: 300px;
		height: 90px;
	}
</style>
