<!-- FloatingShapes.svelte -->
<div class="floating-container">
	<!-- Floating shapes with animations -->
	<div class="floating-shape shape-1">
		<div class="shape-content yellow-square"></div>
	</div>

	<div class="floating-shape shape-2">
		<div class="shape-content blue-circle"></div>
	</div>

	<div class="floating-shape shape-3">
		<div class="shape-content green-square"></div>
	</div>

	<div class="floating-shape shape-4">
		<div class="shape-content purple-circle"></div>
	</div>

	<!-- Big decorative circles -->
	<div class="big-circle circle-1"></div>
	<div class="big-circle circle-2"></div>

	<!-- Dashed lines -->
	<div class="dashed-line line-1"></div>
	<div class="dashed-line line-2"></div>

	<!-- Animated stars -->
	<div class="star star-1">✨</div>
	<div class="star star-2">✨</div>
</div>

<style>
	.floating-container {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		pointer-events: none;
		z-index: 0;
		overflow: hidden;
	}

	.floating-shape {
		position: absolute;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	.shape-content {
		border: 3px solid #000;
		transition: all 0.3s ease;
	}

	/* Shape 1 - Yellow square */
	.shape-1 {
		top: 2.5rem;
		left: 2.5rem;
		animation: float1 6s ease-in-out infinite;
	}

	.yellow-square {
		width: 3rem;
		height: 3rem;
		background-color: #fef08a;
		border-radius: 0.5rem;
		transform: rotate(12deg);
	}

	/* Shape 2 - Blue circle */
	.shape-2 {
		top: 20%;
		right: 15%;
		animation: float2 7s ease-in-out infinite 0.5s;
	}

	.blue-circle {
		width: 4rem;
		height: 4rem;
		background-color: #bfdbfe;
		border-radius: 50%;
	}

	/* Shape 3 - Green square */
	.shape-3 {
		bottom: 25%;
		left: 10%;
		animation: float3 8s ease-in-out infinite 1s;
	}

	.green-square {
		width: 2.5rem;
		height: 2.5rem;
		background-color: #bbf7d0;
		border-radius: 0.5rem;
		transform: rotate(-12deg);
	}

	/* Shape 4 - Purple circle */
	.shape-4 {
		right: 20%;
		bottom: 10%;
		animation: float1 4s ease-in-out infinite 0.2s;
	}

	.purple-circle {
		width: 3.5rem;
		height: 3.5rem;
		background-color: #e9d5ff;
		border-radius: 50%;
	}

	/* Big decorative circles */
	.big-circle {
		position: absolute;
		border: 4px solid #000;
		border-radius: 50%;
		opacity: 0.3;
	}

	.circle-1 {
		top: -5rem;
		left: -5rem;
		width: 10rem;
		height: 10rem;
		background-color: #fef3c7;
	}

	.circle-2 {
		right: -5rem;
		bottom: -5rem;
		width: 14rem;
		height: 14rem;
		background-color: #dbeafe;
	}

	/* Dashed lines */
	.dashed-line {
		position: absolute;
		height: 3px;
		border-top: 3px dashed #000;
		opacity: 0.3;
	}

	.line-1 {
		top: 40%;
		left: 1.25rem;
		width: 4rem;
	}

	.line-2 {
		top: 60%;
		right: 2rem;
		width: 3rem;
	}

	/* Animated stars */
	.star {
		position: absolute;
		font-size: 1.5rem;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	.star-1 {
		top: 30%;
		right: 30%;
		animation: float1 4s ease-in-out infinite 0.2s;
	}

	.star-2 {
		bottom: 40%;
		left: 25%;
		font-size: 1.25rem;
		animation: float2 5s ease-in-out infinite 1.5s;
	}

	/* Keyframe animations */
	@keyframes float1 {
		0%,
		100% {
			transform: translateY(0) rotate(12deg);
		}
		50% {
			transform: translateY(-15px) rotate(15deg);
		}
	}

	@keyframes float2 {
		0%,
		100% {
			transform: translateY(0) rotate(-5deg);
		}
		50% {
			transform: translateY(-20px) rotate(8deg);
		}
	}

	@keyframes float3 {
		0%,
		100% {
			transform: translateY(0) rotate(-12deg);
		}
		50% {
			transform: translateY(-18px) rotate(-8deg);
		}
	}

	/* Dark mode support */
	@media (prefers-color-scheme: dark) {
		.yellow-square {
			background-color: #a16207;
		}

		.blue-circle {
			background-color: #1d4ed8;
		}

		.green-square {
			background-color: #15803d;
		}

		.purple-circle {
			background-color: #7c3aed;
		}

		.circle-1 {
			background-color: #92400e;
		}

		.circle-2 {
			background-color: #1e40af;
		}

		.dashed-line {
			border-color: #6b7280;
		}
	}
</style>
