<svelte:head>
	<title>Atikah · Full-Stack Developer</title>
	<meta
		name="description"
		content="Portfolio of Nurfatin Atikah, a full-stack developer delivering Laravel and SvelteKit platforms for civic and enterprise operations."
	/>
</svelte:head>

<script>
	const navLinks = [
		{ href: '#about', label: 'About' },
		{ href: '#projects', label: 'Projects' },
		{ href: '#experience', label: 'Experience' },
		{ href: '#contact', label: 'Contact' }
	];

	const summaries = [
		'Builds Laravel + SvelteKit platforms that keep operations grounded in real data.',
		'Comfortable working end-to-end: discovery, architecture, delivery, and onboarding.',
		'Focus areas: elections, tenders, internal dashboards, and automation tooling.'
	];

	const skills = [
		{ title: 'Product Delivery', description: 'Scoped and shipped 8+ end-to-end web products for civic and enterprise teams.' },
		{ title: 'Data & Reporting', description: 'Metabase, Supabase, Highcharts, and custom dashboards for quick-read metrics.' },
		{ title: 'Integration Work', description: 'REST APIs, secure auth, Telegram bots, and automated reporting loops.' },
		{ title: 'Steady Operations', description: 'Deployment on Cloudflare & Shinjiru, monitoring, documentation, and training.' }
	];

	const projects = [
		{
			name: 'Tender Management Platform',
			role: 'Lead developer',
			impact: 'Centralised tender listings, company profiles, and reporting so managers stopped relying on spreadsheets.',
			stack: ['Laravel 10', 'MySQL', 'Tailwind', 'Metabase'],
			media: [
				{ src: '/media/tender-01.svg', alt: 'Tender platform dashboard snapshot' },
				{ src: '/media/tender-02.svg', alt: 'Tender submission filtering view' }
			]
		},
		{
			name: 'BARMM Election Operations',
			role: 'Full-stack developer',
			impact: 'Delivered voter data collection and field coordination tools used during regional election prep.',
			stack: ['Laravel 10', 'SQL', 'Role-based access'],
			media: [
				{ src: '/media/barmm-01.svg', alt: 'Election operations status board' },
				{ src: '/media/barmm-02.svg', alt: 'Field coordination workflow screen' }
			]
		},
		{
			name: 'Global Car Trading & Telegram Bot',
			role: 'Backend & automation',
			impact: 'Automated daily deal summaries and tracked transactions across physical and online auctions.',
			stack: ['Laravel 9', 'SQL', 'Telegram Bot'],
			media: [
				{ src: '/media/car-trading-01.svg', alt: 'Car trading inventory overview' },
				{ src: '/media/car-trading-02.svg', alt: 'Telegram automation handoff flow' }
			]
		},
		{
			name: 'Election Readiness Toolkit',
			role: 'Product developer',
			impact: 'Live dashboards and AI summaries that help leadership monitor nationwide field updates.',
			stack: ['Laravel 10', 'Supabase', 'Highcharts'],
			media: [
				{ src: '/media/election-toolkit-01.svg', alt: 'Election readiness summary dashboard' },
				{ src: '/media/election-toolkit-02.svg', alt: 'Incident log and alert feed' }
			]
		}
	];

	const experience = [
		{
			company: 'AGA Touch (M) Sdn Bhd',
			role: 'Software Developer, IT Technical',
			period: 'Sept 2021 – Present',
			points: [
				'Migrated core platforms from Laravel 7 to 10 and introduced modular security patterns.',
				'Rolled out dashboards and training for election, charity, and tender teams across Southeast Asia.'
			]
		},
		{
			company: 'G3 Global Berhad',
			role: 'Data Analyst Intern',
			period: 'Mar 2021 – Aug 2021',
			points: [
				'Prepared executive dashboards using Python, SQL, and Metabase.',
				'Supported Laravel-based initiatives with workflow reviews and QA.'
			]
		}
	];

	const education = [
		{
			program: "Bachelor's Degree · Computer Science (Software Engineering)",
			institution: 'University Malaysia Pahang',
			period: '2017 – 2021'
		},
		{
			program: 'Foundation in Biology Science',
			institution: 'Penang Matriculation College',
			period: '2016 – 2017'
		}
	];

	const contactLinks = [
		{ label: 'Email', value: 'atikahsubari@gmail.com', href: 'mailto:atikahsubari@gmail.com' },
		{ label: 'Phone', value: '+60 17 283 4841', href: 'tel:+60172834841' },
		{ label: 'LinkedIn', value: 'linkedin.com/in/atikahsubari', href: 'https://www.linkedin.com/in/atikahsubari' },
		{ label: 'GitHub', value: 'github.com/atikahas', href: 'https://github.com/atikahas' }
	];

	let activeSlides = projects.map(() => 0);

	const goToSlide = (projectIndex, slideIndex) => {
		if (!projects[projectIndex]?.media?.length) return;
		activeSlides[projectIndex] = slideIndex;
		activeSlides = [...activeSlides];
	};

	const goToPrev = (projectIndex) => {
		const total = projects[projectIndex]?.media?.length ?? 0;
		if (total < 2) return;
		const nextIndex = (activeSlides[projectIndex] - 1 + total) % total;
		goToSlide(projectIndex, nextIndex);
	};

	const goToNext = (projectIndex) => {
		const total = projects[projectIndex]?.media?.length ?? 0;
		if (total < 2) return;
		const nextIndex = (activeSlides[projectIndex] + 1) % total;
		goToSlide(projectIndex, nextIndex);
	};
</script>

<div class="min-h-screen bg-slate-50 text-slate-900">
	<header class="sticky top-0 z-20 border-b border-slate-200 bg-white/95 backdrop-blur">
		<div class="mx-auto flex max-w-5xl items-center justify-between px-5 py-4">
			<a href="#about" class="text-sm font-semibold uppercase tracking-[0.4em] text-slate-700">Atikah</a>
			<nav class="hidden items-center gap-6 text-sm text-slate-600 md:flex">
				{#each navLinks as link}
					<a class="transition hover:text-slate-900" href={link.href}>{link.label}</a>
				{/each}
			</nav>
			<a
				class="rounded-full border border-slate-300 px-4 py-2 text-xs font-semibold uppercase tracking-[0.35em] text-slate-700 transition hover:border-slate-400 hover:text-slate-900"
				href="mailto:atikahsubari@gmail.com"
			>
				Contact
			</a>
		</div>
	</header>

	<main class="mx-auto flex max-w-5xl flex-col gap-24 px-5 pb-24 pt-16">
		<section id="about" class="grid gap-10 md:grid-cols-[1.35fr_0.65fr] md:items-start">
			<div class="space-y-6">
				<p class="text-xs font-semibold uppercase tracking-[0.5em] text-slate-500">Full-stack developer · Klang, MY</p>
				<h1 class="text-4xl font-semibold tracking-tight text-slate-900 md:text-5xl">Builds reliable tools for teams on the ground.</h1>
				<p class="max-w-xl text-base text-slate-600">
					I keep product teams and operations groups aligned by shipping practical Laravel and SvelteKit platforms. The goal is always the same: clear data, calm workflows, and
					results that feel ready for real-world pressure.
				</p>
				<ul class="space-y-3 text-sm text-slate-600">
					{#each summaries as item}
						<li class="flex gap-3">
							<span class="mt-1 h-1.5 w-1.5 flex-shrink-0 rounded-full bg-slate-400"></span>
							<span>{item}</span>
						</li>
					{/each}
				</ul>
				<div class="flex flex-wrap gap-3">
					<a class="rounded-full bg-slate-900 px-6 py-2 text-sm font-semibold text-white transition hover:bg-slate-700" href="#projects">View projects</a>
					<a class="rounded-full border border-slate-300 px-6 py-2 text-sm font-semibold text-slate-700 transition hover:border-slate-400 hover:text-slate-900" href="#experience">
						Experience
					</a>
				</div>
			</div>

			<div class="space-y-6">
				<div class="flex flex-col items-start gap-4 rounded-3xl border border-slate-200 bg-white p-6 shadow-sm">
					<div class="flex h-20 w-20 items-center justify-center rounded-2xl bg-slate-900 text-lg font-semibold uppercase tracking-[0.3em] text-white">NA</div>
					<div>
						<p class="text-base font-semibold text-slate-900">Nurfatin Atikah</p>
						<p class="text-sm text-slate-500">Full-stack partner for ops-heavy releases</p>
					</div>
					<div class="flex flex-wrap gap-2 text-xs uppercase tracking-[0.3em] text-slate-500">
						<span class="rounded-full border border-slate-200 px-3 py-1">Remote-ready</span>
						<span class="rounded-full border border-slate-200 px-3 py-1">MY · SEA</span>
					</div>
				</div>

				<!-- <div class="rounded-3xl border border-slate-200 bg-white p-6 shadow-sm">
					<h2 class="text-sm font-semibold uppercase tracking-[0.3em] text-slate-500">Focus</h2>
					<ul class="mt-4 space-y-2 text-sm text-slate-600">
						<li>Election readiness and field coordination platforms</li>
						<li>Tender and charity operations dashboards</li>
						<li>Automation loops for reporting and comms</li>
					</ul>
				</div> -->
			</div>
		</section>

		<section id="skills" class="space-y-8">
			<div class="flex flex-col gap-2">
				<h2 class="text-2xl font-semibold text-slate-900">Snapshot</h2>
				<p class="max-w-2xl text-sm text-slate-600">A few ways I’ve been useful on recent teams.</p>
			</div>
			<div class="grid gap-4 md:grid-cols-2">
				{#each skills as skill}
					<div class="rounded-3xl border border-slate-200 bg-white p-5 shadow-sm">
						<h3 class="text-base font-semibold text-slate-900">{skill.title}</h3>
						<p class="mt-2 text-sm text-slate-600">{skill.description}</p>
					</div>
				{/each}
			</div>
		</section>

		<section id="projects" class="space-y-8">
			<div class="flex flex-col gap-2">
				<h2 class="text-2xl font-semibold text-slate-900">Selected projects</h2>
				<p class="max-w-2xl text-sm text-slate-600">Real deliverables that moved teams forward.</p>
			</div>
			<div class="space-y-5">
				{#each projects as project}
					<article class="rounded-3xl border border-slate-200 bg-white p-5 shadow-sm">
						<div class="flex flex-col gap-2 md:flex-row md:items-center md:justify-between">
							<div>
								<h3 class="text-base font-semibold text-slate-900">{project.name}</h3>
								<p class="text-sm text-slate-500">{project.role}</p>
							</div>
							<div class="flex flex-wrap gap-2 text-xs uppercase tracking-[0.3em] text-slate-500 md:justify-end">
								{#each project.stack as item}
									<span class="rounded-full border border-slate-200 px-3 py-1">{item}</span>
								{/each}
							</div>
						</div>
						<p class="mt-3 text-sm text-slate-600">{project.impact}</p>
					</article>
				{/each}
			</div>
		</section>

		<section id="experience" class="space-y-8">
			<div class="flex flex-col gap-2">
				<h2 class="text-2xl font-semibold text-slate-900">Experience</h2>
				<p class="max-w-2xl text-sm text-slate-600">Teams I’ve supported and the impact delivered.</p>
			</div>
			<div class="space-y-5">
				{#each experience as role}
					<article class="rounded-3xl border border-slate-200 bg-white p-5 shadow-sm">
						<div class="flex flex-col gap-2 md:flex-row md:items-center md:justify-between">
							<div>
								<h3 class="text-base font-semibold text-slate-900">{role.role}</h3>
								<p class="text-sm text-slate-500">{role.company}</p>
							</div>
							<p class="text-sm text-slate-500">{role.period}</p>
						</div>
						<ul class="mt-3 space-y-2 text-sm text-slate-600">
							{#each role.points as point}
								<li class="flex gap-3">
									<span class="mt-1 h-1.5 w-1.5 flex-shrink-0 rounded-full bg-slate-400"></span>
									<span>{point}</span>
								</li>
							{/each}
						</ul>
					</article>
				{/each}
			</div>
		</section>

		<section id="education" class="space-y-8">
			<div class="flex flex-col gap-2">
				<h2 class="text-2xl font-semibold text-slate-900">Education</h2>
			</div>
			<div class="space-y-4">
				{#each education as item}
					<div class="rounded-3xl border border-slate-200 bg-white p-5 shadow-sm">
						<p class="text-sm font-semibold text-slate-900">{item.program}</p>
						<p class="text-sm text-slate-500">{item.institution}</p>
						<p class="text-xs uppercase tracking-[0.3em] text-slate-500">{item.period}</p>
					</div>
				{/each}
			</div>
		</section>

		<section id="contact" class="space-y-8">
			<div class="flex flex-col gap-2">
				<h2 class="text-2xl font-semibold text-slate-900">Let’s talk</h2>
				<p class="max-w-2xl text-sm text-slate-600">Send a note with your context and we’ll line up the next steps.</p>
			</div>
			<div class="grid gap-4 md:grid-cols-2">
				{#each contactLinks as contact}
					<a class="rounded-3xl border border-slate-200 bg-white p-5 text-sm text-slate-600 shadow-sm transition hover:border-slate-300 hover:text-slate-900" href={contact.href}>
						<span class="block text-xs uppercase tracking-[0.3em] text-slate-500">{contact.label}</span>
						<span class="mt-2 block text-base text-slate-900">{contact.value}</span>
					</a>
				{/each}
			</div>
		</section>
	</main>

	<footer class="border-t border-slate-200 bg-white">
		<div class="mx-auto flex max-w-5xl flex-col gap-3 px-5 py-6 text-sm text-slate-500 md:flex-row md:items-center md:justify-between">
			<p>© {new Date().getFullYear()} Nurfatin Atikah Ahmad Subari</p>
			<div class="flex gap-4">
				{#each navLinks as link}
					<a class="transition hover:text-slate-900" href={link.href}>{link.label}</a>
				{/each}
			</div>
		</div>
	</footer>
</div>
