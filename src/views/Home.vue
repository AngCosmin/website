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

		<!-- <div class="card">
			<div class="header">
				<h3>Raspberry Pi Robot</h3>
			</div>
			
			<div class="content">
				<img :src="getBannerPath('project_raspberry.png')">

				<p>
					This project is my final bachelor degree project.
					The robot can be controlled over the internet using a mobile 
					application made in React Native which connect to a NodeJS server 
					and communication between them is made using websockets.
				</p>
				<p>
					Server interface is made using Electron and it display the 
					status of mobile application and robot application. 
					Robot application is made in Python and use websockets 
					to connect to server and OpenCV for ball tracking.
				</p>
				<p>
					You can find some DEMOs here:
					<a href="https://youtu.be/kGCDWxzGauA" target="_blank">demo 1</a>,
					<a href="https://youtu.be/4IdgQTjr4aY" target="_blank">demo 2</a>
					and
					<a href="https://youtu.be/h1N25ActYt4" target="_blank">demo 3</a>.
				</p>
			</div>

			<div class="read-more">
				Read more
			</div>
			
			<div class="footer">
				<span class="skill">Python</span>
				<span class="skill">Javascript</span>
				<span class="skill">NodeJS</span>
				<span class="skill">Websockets</span>
				<span class="skill">ReactNative</span>
				<span class="skill">Electron</span>
			</div>
		</div> -->

		<Project title="Raspberry Pi Robot" 
				 :showReadMore="true" 
				 :technologies="['Python', 'Javascript', 'NodeJS', 'Websockets', 'React Native', 'Electron', 'OpenCV']">
				 
			<img :src="getBannerPath('project_raspberry.png')">

			<p>
				This project is my final bachelor degree project.
				The robot can be controlled over the internet using a mobile 
				application made in React Native which connect to a NodeJS server 
				and communication between them is made using websockets.
			</p>
			<p>
				Server interface is made using Electron and it display the 
				status of mobile application and robot application. 
				Robot application is made in Python and use websockets 
				to connect to server and OpenCV for ball tracking.
			</p>
			<p>
				You can find some DEMOs here:
				<a href="https://youtu.be/kGCDWxzGauA" target="_blank">demo 1</a>,
				<a href="https://youtu.be/4IdgQTjr4aY" target="_blank">demo 2</a>
				and
				<a href="https://youtu.be/h1N25ActYt4" target="_blank">demo 3</a>.
			</p>
		</Project>

		<Project title="PC Remote Control" 
				 :showReadMore="true" 
				 :technologies="['C#', 'Javascript', 'Socket.IO', 'HTML/CSS']">
			<img :src="getBannerPath('project_remote.jpg')">

			<p>
				This project was made in my first year of university for a competition. 
				I won 3rd place and popularity prize (most voted project by the people 
				who were there). Desktop application is made in C# and the web application 
				is made with HTML, CSS and Javascript. Both of them are connected to a 
				NodeJS server to communicate.
			</p>
			<p>
				You can find some DEMOs here:
				<a href="https://youtu.be/sTcxUzsQRmc" target="_blank">demo 1</a> 
				and
				<a href="https://youtu.be/6QNPjJNgTrA" target="_blank">demo 2</a>
			</p>
		</Project>

		<Project title="Personal website" :technologies="['VueJS', 'Typescript']">
			<img :src="getBannerPath('project_website.jpg')">
		</Project>

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
import Terminal from "@/components/Terminal.vue";
import Project from "@/components/Project.vue";

@Component({
	components: {
		Terminal,
		Project,
	},
	methods: {
		getBannerPath (filename) {
			return filename ? require(`../assets/img/${filename}`) : ''
		}
	},
})
export default class Home extends Vue {}
</script>
