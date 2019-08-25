<template>
	<div class="container">
		<div class="nav">
			<a href="#">Home</a>
			<a href="#projects">Projects</a>
			<a href="#contact">Contact</a>
			<a href="https://drive.google.com/open?id=1GkK6NopJL8TybvBktO33AiwK6Rxkt-7j">Resume</a>
		</div>

		<div class="hero-logo">
			Home Sensors<span class="cursor-main-color">&nbsp</span>
		</div>

		<div class="terminal">
			<div class="bar">
				<div class="button red"></div>
				<div class="button yellow"></div>
				<div class="button green"></div>
			</div>

			<div class="screen">
				<p class="command">home.temperature</p>
				<p v-if="temperature" class="response">{{ temperature.value }}&deg;C - Updated {{ temperature.time_ago }}</p>
				<p v-else class="response">Data unavailable</p>

				<p class="command">home.humidity</p>
				<p v-if="humidity" class="response">{{ humidity.value }}% - Updated {{ humidity.time_ago }}</p>
				<p v-else class="response">Data unavailable</p>
				
				<p class="command" style="margin-top: 150px">
					<span class="cursor-white">&nbsp</span>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
import { Component, Vue } from "vue-property-decorator"
import axios from 'axios'

export default {
	data() {
		return {
			temperature: null,
			humidity: null,
		}
	},
	mounted () {
		this.$nextTick(function () {
            window.setInterval(() => {
				axios.get('http://cosmin-home.herokuapp.com/sensors').then(response => {
					this.temperature = response.data.temperature
					this.humidity = response.data.humidity
				})
            },1000);
        })
	}
}
</script>
