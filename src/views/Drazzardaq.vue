<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

const date = new Date().valueOf();

const resources = [
	{ image: 'creativenetfx.png', badge: 'CreativeNetFX', title: 'Front-end Developer and SEO Manager', text: '2013 - 2014' },
	{ image: 'microbusiness.jpg', badge: 'MicroBusiness', title: 'Junior Java Developer', text: '2015 - 2016' },
	{ image: 'logoipsum.png', badge: 'Adaxions', title: 'CTO and Founder', text: '2017 - 2018' },
	{ image: 'xenovation.png', badge: 'Xenovation', title: 'Joomla Developer', text: '2018 - 2019' },
	{ image: 'ntos.png', badge: 'NTOS', title: 'IT Consultant', text: '2020 - 2021' },
	{ image: 'seypro.jpg', badge: 'SEYPRO', title: 'Web Developer', text: '2021 - 2023' },
	];

const techs = [
	{ name: 'Apache', image: 'apache-logo.png' },
	{ name: 'Git', image: 'git-logo.png' },
	{ name: 'GitHub', image: 'github-logo.png' },
	{ name: 'PHP', image: 'php-logo.png' },
	{ name: 'MySQL', image: 'mysql-logo.png' },
	{ name: 'HTML', image: 'html-logo.png' },
	{ name: 'CSS', image: 'css-logo.png' },
	{ name: 'JavaScript', image: 'js-logo.png' },
	{ name: 'Laravel', image: 'laravel-logo.png' },
	{ name: 'Vue.js', image: 'vuejs-logo.png' },
	{ name: 'Tailwind CSS', image: 'tailwindcss-logo.png' },
	{ name: 'AWS', image: 'aws-logo.png' },
	{ name: 'Linux', image: 'linux-logo.png' },
	{ name: 'GNOME', image: 'gnome-logo.png' },
	{ name: 'axios', image: 'axios-logo.png' },
	{ name: 'Symfony', image: 'symfony-logo.png' },
	{ name: 'Jetstream', image: 'jetstream-logo.png' },
	{ name: 'Fortify', image: 'fortify-logo.png' },
	{ name: 'Sanctum', image: 'sanctum-logo.png' },
	{ name: 'MetaMask', image: 'metamask-logo.png' },
	{ name: 'Vite', image: 'vite-logo.png' },
	{ name: 'inertia', image: 'inertia-logo.png' },
	{ name: 'heroicons', image: 'heroicons-logo.png' },
	{ name: 'Babylon', image: 'babylon-logo.png' },
	{ name: 'NodeJS', image: 'nodejs-logo.png' },
	{ name: 'composer', image: 'composer-logo.png' },
	{ name: 'npm', image: 'npm-logo.png' },
	{ name: 'webpack', image: 'webpack-logo.png' },
	{ name: 'FontAwesome', image: 'fontawesome-logo.png' },
	{ name: 'Krita', image: 'krita-logo.png' },
	{ name: 'Pexels', image: 'pexels-logo.png' },
	{ name: 'TheNounProject', image: 'thenounproject-logo.png' },
	{ name: 'Vectary', image: 'vectary-logo.png' },
	{ name: 'Freepik', image: 'freepik-logo.png' },
	{ name: 'GoogleFonts', image: 'googlefonts-logo.png' },
	{ name: 'VSCode', image: 'vscode-logo.png' },
];

const topbar = ref(false);
const scroll = (event) => {
	const header = document.querySelector('.dheader');

	const headerHeight = header.offsetHeight;
	if (event.target.children[0].scrollTop > headerHeight) topbar.value = true;
	else topbar.value = false;
};
 
onMounted(() => {
  window.addEventListener('scroll', scroll, false);
});
   
onUnmounted(() => {
  window.removeEventListener('scroll', scroll);
});

const getTechImage = (tech) => {
	return 'images/logos/techs/' + tech;
};

const getCompanyImage = (company) => {
	return 'images/logos/companies/' + company;
};
</script>

<template>
	<div class="flex flex-col items-start justify-start font-mono tracking-normal">
		<div class="flex items-center justify-start px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32 w-full fixed top-0 h-[50px] max-h-[50px] min-h-[50px] z-50 transition" :class="topbar ? 'bg-black' : 'bg-white'">
			<nav class="flex items-center w-full justify-between mr-1" :class="topbar ? 'text-white hover:text-white' : 'text-black hover:text-black'">
				<p class="mb-0 mr-2 sm:mr-4 font-bold uppercase text-sm">Hi! I'm Drago<span class="hidden sm:inline">, the Web Developer</span>.</p>
				<a href="mailto:randjelovicdragoljub1@gmail.com?subject=Hi%20Drago!%20I%20have%20something%20to%20tell%20you..." class="mr-2 sm:mr-4">Email</a>
				<a href="https://wa.me/38169698442?text=Hi%20Drago!%20I%20have%20something%20to%20tell%20you...">WhatsApp</a>
				<a href="@/Resume.pdf" class="ml-auto" download>Resume</a>
			</nav>
		</div>

		<div class="page -mt-[30px]">
			<div class="h-[33vh] min-h-[33vh] max-h-[33vh] overflow-hidden bg-primary flex relative items-center justify-center dheader">
				<div class="flex flex-col z-40 text-white w-full items-center justify-center">
					<img src="@/images/Dragoljub.jpg" alt="Dragoljub Ranđelović" title="Dragoljub Ranđelović" class="rounded-xl h-32 w-32 mb-3 border-4">
					<div class="flex items-center justify-center">
						<a href="https://www.linkedin.com/in/drazzardaq" target="_blank" class="text-white hover:text-white">LinkedIn</a>
					</div>
				</div>
			</div>
			<div class="flex flex-col px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32 py-12 md:py-16 bg-white">
				<h1 class="text-primary">Experiences</h1>
				<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-6">
					<div v-for="resource in resources" class="flex flex-col border-4 border-primary bg-white rounded-xl">
						<div class="py-5 px-3 flex items-center justify-center">
							<img :src="getCompanyImage(resource.image)" :alt="resource.badge + ' Logo'" :title="resource.badge + ' Logo'" class="w-auto h-8" :class="resource.badge === 'MicroBusiness' && 'rounded-lg'">
						</div>
						<div class="flex flex-col p-4 bg-primary text-white">
							<h3>{{ resource.badge }}</h3>
							<p class="mb-0">{{ resource.title }}</p>
							<p>{{ resource.text }}</p>
						</div>
					</div>
				</div>
			</div>
			<div class="bg-primary py-12 md:py-16 lg:py-24 xl:py-32 text-white px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32">
				<div class="flex flex-col">
					<h1>Education</h1>
					<p>ICT College of Vocational Studies, Belgrade, Serbia</p>
					<p>BCompSc, University Braća Karić, Belgrade, Serbia</p>
				</div>
			</div>
			<div class="triangle triangle-top"></div>
			<div class="py-12 md:py-16 lg:py-24 xl:py-32 px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32">
				<div class="flex flex-col">
					<h1>Portfolio</h1>
					<p>Besidea many contract-based and NDA-based projects, I'm working on a few open-source projects.</p>
					<div class="flex flex-wrap items-center justify-start mt-5 mb-1">
						<a href="https://github.com/drazzardaq/coremopen.git" target="_blank" class="flex items-center mb-5 mr-7">
							<img src="@/images/projects/coremopen.png" alt="Corem open-source" title="Corem open-source" class="mr-2 w-auto h-10" />
						</a>
						<a href="https://github.com/drazzardaq/dolphinal" target="_blank" class="flex items-center mb-5 mr-7 text-[#f78419]">
							<img src="@/images/projects/dolphinal.png" alt="Dolphinal Project" title="Dolphinal Project" class="mr-2 w-10 h-10" />
							<span>Dolphinal</span>
						</a>
						<a href="https://github.com/drazzardaq/resume-v1" target="_blank" class="flex items-center mb-5 mr-7">
							<img src="@/images/Dragoljub.jpg" alt="Resume v1" title="Resume v1" class="rounded-xl mr-2 w-10 h-10" />
							<div class="flex flex-col">
								<span class="text-xl tracking-widest font-light -mb-1">Resume v1</span>
							</div>
						</a>
						<a href="https://github.com/drazzardaq/resume-v2" target="_blank" class="flex items-center mb-5 mr-7">
							<img src="@/images/Dragoljub.jpg" alt="Resume v2" title="Resume v2" class="border-2 border-white shadow-lg rounded-full mr-2 w-10 h-10" />
							<div class="flex flex-col">
								<span class="text-xl -mb-1">Resume v2</span>
							</div>
						</a>
					</div>
					<p>The source codes of these projects are hosted on my <a href="https://github.com/drazzardaq" target="_blank" class="text-black hover:text-black">GitHub</a> account.</p>
				</div>
			</div>
			<div class="py-12 md:py-16 lg:py-24 xl:py-32 px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32">
				<div class="flex flex-col">
					<h1>Technical Expertise</h1>
					<div class="flex items-center flex-wrap my-3">
						<img v-for="tech in techs" :key="tech.name" :src="getTechImage(tech.image)" :alt="tech.name" :title="tech.name" class="my-3 mr-3 w-10 h-10">
					</div>
				</div>
			</div>
			<div class="py-12 md:py-16 lg:py-24 xl:py-32 px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32">
				<div class="flex flex-col">
					<h1>Testimonials</h1>
					<p>Here is what my clients say about me.</p>
					<div class="flex items-start flex-wrap">
					<img src="@/images/testimonial2.png" alt="Testimonial" class="w-mi mt-5 mr-5">
					<img src="@/images/testimonial.png" alt="Testimonial" class="w-min mt-5">
					</div>
					<p class="mt-5">For more reviews, please visit <a href="https://www.freelancer.com/get/Dragoljub?f=give" target="_blank" class="text-[#0193cf] hover:text-[#0193cf]">Freelancer</a>.</p>
				</div>
			</div>
			<div class="py-12 md:py-16 lg:py-24 xl:py-32 px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32 relative">
				<div class="flex flex-col">
					<h1>Support</h1>
					<p>If you want to support me, please hit the GitHub Sponsors button.</p>
					<a href="https://github.com/sponsors/drazzardaq?o=esb" target="_blank">
						<svg aria-hidden="true" viewBox="0 0 24 24" version="1.1" class="fill-[#bf4b8a] hover:fill-[#db61a2] cursor-pointer w-20 h-20 mt-3">
							<path d="m12 20.703.343.667a.748.748 0 0 1-.686 0l-.003-.002-.007-.003-.025-.013a31.138 31.138 0 0 1-5.233-3.576C3.8 15.573 1 12.332 1 8.514v-.001C1 5.053 3.829 2.5 6.736 2.5 9.03 2.5 10.881 3.726 12 5.605 13.12 3.726 14.97 2.5 17.264 2.5 20.17 2.5 23 5.052 23 8.514c0 3.818-2.801 7.06-5.389 9.262a31.148 31.148 0 0 1-5.233 3.576l-.025.013-.007.003-.002.001ZM6.736 4C4.657 4 2.5 5.88 2.5 8.514c0 3.107 2.324 5.96 4.861 8.12a29.655 29.655 0 0 0 4.566 3.175l.073.041.073-.04c.271-.153.661-.38 1.13-.674.94-.588 2.19-1.441 3.436-2.502 2.537-2.16 4.861-5.013 4.861-8.12C21.5 5.88 19.343 4 17.264 4c-2.106 0-3.801 1.389-4.553 3.643a.751.751 0 0 1-1.422 0C10.537 5.389 8.841 4 6.736 4Z"></path>
						</svg>
					</a>
				</div>
			</div>
			<div class="triangle triangle-bottom"></div>
			<div class="bg-primary text-white py-12 md:py-16 lg:py-24 xl:py-32 px-6 sm:px-8 md:px-12 lg:px-20 xl:px-32">
				<div class="flex flex-col">
					<h1>Personality</h1>
					<p>I consider myself a creative, intuitive, and eclectic person.</p>
					<p>People say I'm the one who gets the job done.</p>
					<p>Besides loving my job, I also enjoy time, family, and sightseeing concepts.</p>
				</div>
			</div>
			<div class="flex flex-col items-center justify-center w-full py-3 bg-black text-xs text-white">
				<a href="https://twitter.com/drazzardaq" target="_blank" class="text-white hover:text-white mb-2">X</a>
				<span class="block">Dragoljub Ranđelović @ {{ date }}</span>
			</div>
		</div>
	</div>
</template>
