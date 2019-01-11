<template>
	<div class="container">
		<div class="nav">
			<a href="#">Home</a>
			<a href="#projects">Projects</a>
			<a href="#contact">Contact</a>
			<a href="https://drive.google.com/open?id=1GkK6NopJL8TybvBktO33AiwK6Rxkt-7j">Resume</a>
		</div>

		<div class="hero-logo">
			Cosmin_Anghel<span class="cursor-main-color">&nbsp</span>
		</div>

		<div class="hero-description">
			Developer with full of professionalism and of course the thing called "Passion". I am responsible and hard-working person with good communication and fast-learning skills. I am very dedicated and I'm trying to develop new skills everyday.
		</div>

		<terminal></terminal>
		
		<div id="projects" class="section">Projects</div>

		<div class="card">
			<div class="header">
				<h3>Raspberry Pi Robot</h3>
			</div>
			<img :src="getBannerPath('project_raspberry.png')" class="banner">
			
			<div class="content">
				<p style="color: rgb(55, 61, 63);">
					This project is my final bachelor degree project.
					The robot can be controlled over the internet using a mobile 
					application made in React Native which connect to a NodeJS server 
					and communication between them is made using websockets.
				</p>
				<p style="color: rgb(55, 61, 63);">
					Server interface is made using Electron and it display the 
					status of mobile application and robot application. 
					Robot application is made in Python and use websockets 
					to connect to server and OpenCV for ball tracking.
				</p>
				<p style="color: rgb(55, 61, 63);">
					<a href="https://youtu.be/kGCDWxzGauA" target="_blank">DEMO 1</a>
					/
					<a href="https://youtu.be/4IdgQTjr4aY" target="_blank">DEMO 2</a>
					/
					<a href="https://youtu.be/h1N25ActYt4" target="_blank">DEMO 3</a>
				</p>
			</div>
			
			<div class="footer">
				<span class="skill">Python</span>
				<span class="skill">Javascript</span>
				<span class="skill">NodeJS</span>
				<span class="skill">Websockets</span>
				<span class="skill">React Native</span>
				<span class="skill">Electron</span>
			</div>

			<div class="read-more">
				Read more
			</div>
		</div>


		<div class="card"><div class="header"><h3>PC Remote Control</h3></div><img src="/img/project_remote.cf1df817.jpg" class="banner"><div class="content"><p style="color: rgb(55, 61, 63);">This project was made in my first year of university for a competition. I won 3rd place and popularity prize (most voted project by the people who were there). Desktop application is made in C# and the web application is made with HTML, CSS and Javascript. Both of them are connected to a NodeJS server to communicate. You can check these demos:</p><p style="color: rgb(55, 61, 63);"><a href="https://youtu.be/sTcxUzsQRmc" target="_blank">DEMO 1</a>&nbsp;/&nbsp;<a href="https://youtu.be/1u5xv8drxiA" target="_blank">DEMO 2</a>&nbsp;/&nbsp;<a href="https://youtu.be/6QNPjJNgTrA" target="_blank">DEMO 3</a></p></div><div class="footer"><span class="skill">C#</span><span class="skill">Javascript</span><span class="skill">Socket.IO</span><span class="skill">HTML/CSS</span></div></div>

		<div class="card"><div class="header"><h3>Personal website</h3></div><img src="/img/project_website.801f0229.jpg" class="banner"><div class="content"></div><div class="footer"><span class="skill">NodeJS</span><span class="skill">VueJS</span><span class="skill">MongoDB</span></div></div>

		<div id="contact" class="section">Contact</div>

		<div class="contact">
			<div class="email">anghelcosminandrei@gmail.com</div>

			<a href="https://github.com/CosminZoRR" class="link"><i class="fa fa-github fa-2x" aria-hidden="true"></i></a>
			<a href="https://linkedin.com/in/cosminanghel" class="link"><i class="fa fa-linkedin fa-2x" aria-hidden="true"></i></a>
			<a href="https://facebook.com/ang.cosmin" class="link"><i class="fa fa-facebook fa-2x" aria-hidden="true"></i></a>
			<a href="https://instagram.com/angcosmin" class="link"><i class="fa fa-instagram fa-2x" aria-hidden="true"></i></a>
		</div>	
	</div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Component({
	components: {
		HelloWorld
	},
	methods: {
		getBannerPath (filename) {
			return filename ? require(`../assets/img/${filename}`) : ''
		}
	},
})
export default class Home extends Vue {}
</script>
