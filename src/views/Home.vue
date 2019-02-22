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

		<Project title="Simple iOS weather app" 
				 :showReadMore="false" 
				 :technologies="['Swift', 'Alamofire', 'Cocoapods']">
	 
			<img class="banner" :src="getBannerPath('project_weather.png')">

			<p>
				The application automatically get your location based on location service. 
				If your location cannot be determined then you can still open a new tab where 
				you enter city name and then you press a button and now you have the weather for that city.
			</p>
			<p>
				You can find the repo
				<a href="https://github.com/AngCosmin/ios-weather-app" target="_blank">here</a>
			</p>
		</Project>

		<Project title="Emotion based music player" 
				 :showReadMore="false" 
				 :technologies="['Python', 'PyQt', 'Microsoft Cognitive Services', 'OpenCV']">
	 
			<img class="banner" :src="getBannerPath('project_emotions.png')">

			<p>
				This application is a desktop app made with PyQt. It accesses your webcam 
				and continuously checks for your emotions in background. Using the dominant
				emotion from last minute and YouTube API, it searches for a song, downloads it
				and adds it to queue.
			</p>
			<p>
				You can also skip the songs if you don't like them and it will play another song
				for you. The application also has a history, so you don't have to worry about
				repeating songs. 
			</p>
			<p>
				You can find the repo
				<a href="https://github.com/AngCosmin/emotion-based-music-player" target="_blank">here</a>
			</p>
		</Project>

		<Project title="Raspberry Pi Robot" 
				 :showReadMore="false" 
				 :technologies="['Python', 'Javascript', 'NodeJS', 'Websockets', 'React Native', 'Electron', 'OpenCV']">
				 
			<img class="banner" :src="getBannerPath('project_raspberry.png')">

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
			<p>
				You can find the repo
				<a href="https://github.com/AngCosmin/final-project-robot" target="_blank">here</a>
			</p>
		</Project>

		<Project title="PC Remote Control" 
				 :showReadMore="false" 
				 :technologies="['C#', 'Javascript', 'Socket.IO', 'HTML/CSS']">
			<img class="banner" :src="getBannerPath('project_remote.jpg')">

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

		<Project title="Hackathon at Mondly" 
				 :showReadMore="false" 
				 :technologies="['NodeJS', 'Socket.IO', 'Javascript', 'PHP', 'Laravel']">
			<img class="banner" :src="getBannerPath('mondly.jpeg')">

			<p class="center"><img :src="getIcon('trophy.png')"> 2nd place</p>

			<p>
				Me and my teammate created a multiplayer quiz game for learning new languages. 
				We had 10 hours and this is what we did: rooms system, chat per room, multiple game modes, 
				getting points for correct answers and leaderboard.
			</p>
			<p>
				You can find the repo
				<a href="https://github.com/AngCosmin/mondly-challange" target="_blank">here</a>
			</p>
		</Project>

		<Project title="Personal website" :technologies="['HTML/CSS', 'VueJS', 'Typescript']">
			<img class="banner" :src="getBannerPath('project_website.png')">
		</Project>

		<div id="contact" class="section">Contact</div>

		<div class="contact">
			<div class="email">anghelcosminandrei@gmail.com</div>
			<div class="links">
				<a href="https://github.com/angcosmin">Github</a>
				<a href="https://instagram.com/angcosmin">Instagram</a>
				<a href="https://linkedin.com/in/cosminanghel">LinkedIn</a>
				<a href="https://facebook.com/ang.cosmin">Facebook</a>
			</div>
		</div>	
	</div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import Terminal from "@/components/Terminal.vue"
import Project from "@/components/Project.vue"

@Component({
	components: {
		Terminal,
		Project,
	},
	methods: {
		getBannerPath (filename) {
			return filename ? require(`@/assets/img/${filename}`) : ''
		},
		getIcon (filename) {
			return filename ? require(`@/assets/icons/${filename}`) : ''
		},
	},
})
export default class Home extends Vue {}
</script>
