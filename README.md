<HTML>

<title>Задание №1</title>

<body>

<canvas id='lab01' height='500' width='500' style='border:1px solid'></canvas>

<script>
	let canvas = document.getElementById('lab01');
	let ctx = canvas.getContext('2d');

	ctx.fillStyle = '#00dd55'

	t = 0.1
	setInterval(
		function(){
			ctx.clearRect(0, 0, canvas.width, canvas.height);
			let xO = 250, yO = 250, xScale = 160, yScale = 100;
			let x = xO + xScale*Math.cos(t)
			let y = yO + yScale*Math.sin(t)
			ctx.fillRect(xO, yO, 5, 5);
			ctx.fillRect(x, y, 5, 5);
			let i = 0;
			for (;i < x - xO; ++i){
				ctx.fillRect(xO + i, y + 1, 3, 3);
			}

			i = 0;
			for (;i < xO - x; ++i){
				ctx.fillRect(xO - i, y + 1, 3, 3);
			}

			i = 0;
			for (;i < y - yO; ++i){
				ctx.fillRect(xO + 1, y + 2 - i, 3, 3);
			}

			i = 0;
			for (;i < yO - y; ++i){
				ctx.fillRect(xO + 1, y + 2 + i, 3, 3);
			}

			t += 0.01
		},
		1,
	);
</script>

</body>
</HTML>
