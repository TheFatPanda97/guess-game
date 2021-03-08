<template>
	<div>
		<h1 id="title">Welcome to Guess Game!</h1>
		<div id="form">
			<input v-model="guess" type="number" placeholder="Enter a number" />
			<button @click="onGuess" class="guess-btn">Guess</button>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			guess: 0,
			secretNum: Math.round(Math.random() * 10),
		}
	},
	methods: {
		onGuess() {
			let msg
			if (this.guess > this.secretNum) {
				msg = "your guess was too big!"
			} else if (this.guess < this.secretNum) {
				msg = "your guess was too small"
			} else {
				msg = "you guessed correctly, yayyyyy! The game has restarted."
                this.secretNum = Math.round(Math.random() * 10)
			}

			alert(msg)
		},
	},
}
</script>

<style scoped>
#title {
	text-align: center;
}

#form {
	text-align: center;
}

input {
	margin: 0px 5px;
}

.guess-btn {
	background-color: black;
	color: white;
	border: none;
	width: 60px;
	height: 20px;
	border-radius: 15%;
}
</style>