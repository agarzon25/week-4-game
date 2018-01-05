$(document).ready(function() {
	let wins = 0;
	let losses = 0;
	let icon_value = 0;
	let values = [];
	let goal_value = 0;
	let curr_score = []; 

	//set random values for crystals
	function setvalues() {
		goal_value = Math.floor((Math.random() * 120) + 19 )
		console.log('goal_value: ' + goal_value)
		$(".win_num").html(goal_value)
		for (let i=1; i<=4; i++) {
			icon_value = Math.floor((Math.random() * 12) + 1 );
			console.log('icon_value' + i + ': ' + icon_value);
			$("#icon" + i).attr('value', icon_value);
			values.push(icon_value)
		}
		console.log(goal_value, values)
	}

	//calculate your score
	function score() {
		let sum_score = 0;
		for (let j=0; j < curr_score.length; j++) {
			sum_score += curr_score[j];
		}
		return sum_score
	}

	//reset all values
	function reset() {
		$("#score").html(0)
		curr_score.length = []
		console.log(curr_score.length)
		curr_score = []
		setvalues()
	}

	//main
	setvalues();
	for (let i=1; i<=4; i++) {
		$("#icon" + i).click(function() {
			console.log(values[i-1])
			curr_score.push(values[i-1])
			console.log(curr_score)
			$("#score").html(score())
			if (score() === goal_value) {
				alert('Winner!')
				wins++
				$("#wins").html("Wins: " + wins)
				reset()

			} else if (score() > goal_value) {
				alert('You lose!')
				losses++
				$("#losses").html("Losses: " + losses)
				reset()
			}
			console.log('your score is ' + score())
		})
	}
})