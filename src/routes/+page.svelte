<svelte:head>
	<title>Nurfatin Atikah · Futuristic Web Developer Portfolio</title>
	<meta
		name="description"
		content="Nurfatin Atikah is a software developer crafting performant, data-rich web applications with Laravel, SvelteKit, Supabase, and modern tooling."
	/>
</svelte:head>

<script>
	const navLinks = [
		{ href: '#profile', label: 'Profile' },
		{ href: '#skills', label: 'Skills' },
		{ href: '#expertise', label: 'Expertise' },
		{ href: '#projects', label: 'Case Studies' },
		{ href: '#experience', label: 'Experience' },
		{ href: '#education', label: 'Education' },
		{ href: '#contact', label: 'Contact' }
	];

	const highlightStats = [
		{ label: 'End-to-end products launched', value: '8+' },
		{ label: 'Stakeholder trainings hosted', value: '25+' },
		{ label: 'Years in full-stack delivery', value: '3+' }
	];

	const professionalSkills = [
		{
			title: 'Full-Stack Web Development',
			description: 'Laravel 8–10, SvelteKit, Supabase, WordPress, modular Blade components, and progressive enhancement patterns.'
		},
		{
			title: 'UI/UX Implementation',
			description: 'Translating wireframes into accessible interfaces with Tailwind CSS, responsive layouts, state management, and design system stewardship.'
		},
		{
			title: 'REST API Development & Integration',
			description: 'Crafting and consuming secure APIs, integrating third-party data (NewsAPI, Google Maps), and hardening authentication flows.'
		},
		{
			title: 'Data Visualization',
			description: 'Metabase, Google Data Studio, Chart.js, Highcharts, and custom dashboards that surface insights in real time.'
		},
		{
			title: 'AI-Enhanced Workflows & Automation',
			description: 'Leveraging ChatGPT, JuliusAI, Google AI Studio, and bespoke scripts to speed content production and decision-ready reporting.'
		},
		{
			title: 'Deployment & Hosting',
			description: 'Cloudflare, Shinjiru hosting, Apache, Git-based automation, and environment hardening with logging and monitoring.'
		}
	];

	const specialties = [
		{
			title: 'Insightful Experiences',
			description:
				'Designing human-centered journeys across internal and civic dashboards, emphasizing clarity of insight, fast time-to-value, and accessibility.',
			points: ['Data storytelling', 'Design systems', 'Accessibility-first']
		},
		{
			title: 'Operational Platforms',
			description:
				'Building mission-critical applications for elections, tenders, and field teams with Laravel, SQL, and structured workflows.',
			points: ['Secure access', 'Workflow optimisation', 'Reliability']
		},
		{
			title: 'Full-Stack Delivery',
			description:
				'Shipping production-ready features end-to-end with Laravel, Supabase, REST APIs, and automated pipelines powered by Cloudflare, Git hooks, and Shinjiru hosting.',
			points: ['Secure auth', 'Data automation', 'CI/CD hygiene']
		}
	];

	const projects = [
		{
			name: 'Tender Management Platform',
			role: 'Web Application Development',
			brief:
				'Digital platform centralising company profiles, tender participation, and project tracking with automated listings and performance analytics.',
			contributions: [
				'Conducted stakeholder interviews to capture requirements and prioritise feature rollout.',
				'Architected the system and database schema from first principles.',
				'Developed company, tender, and reporting modules with robust filtering and document workflows.',
				'Built real-time dashboards surfacing tender statistics and performance trends.',
				'Handled QA, deployment, documentation, and user training end-to-end.'
			],
			tags: ['Laravel 10', 'MySQL', 'Tailwind CSS', 'Metabase']
		},
		{
			name: 'Bangsamoro Autonomous Region in Muslim Mindanao (BARMM)',
			role: 'Web Application Development',
			brief:
				'Mission support system for regional election operations with tiered access, voter data collection, and field coordination tooling.',
			contributions: [
				'Interviewed administrators and ground coordinators to refine workflows and permissions.',
				'Designed architecture and database schema for scalable field data capture.',
				'Developed twin Laravel 10 applications with SQL integrations and secure session handling.',
				'Optimised performance via iterative testing with field teams.',
				'Delivered maintenance, updates, manuals, and user training.'
			],
			tags: ['Laravel 10', 'SQL', 'Access Control', 'Operational dashboards']
		},
		{
			name: 'Maldivian Presidential Election Platform',
			role: 'Web Application Development',
			brief:
				'Comprehensive application enabling multi-tiered election operations, data integrity, and streamlined workflows for national stakeholders.',
			contributions: [
				'Partnered with stakeholders to formalise requirements and risk scenarios.',
				'Engineered architecture, tech selections, and database design.',
				'Built Laravel 9 backends with SQL, ensuring secure data flows and auditability.',
				'Tuned performance and resolved defects based on live testing feedback.',
				'Delivered training, manuals, and long-term maintenance.'
			],
			tags: ['Laravel 9', 'SQL', 'Governance', 'Training']
		},
		{
			name: 'Global Car Trading Platform & Telegram Bot',
			role: 'Web Application & Automation Development',
			brief:
				'Platform supporting physical and online auctions, tracking interests, purchases, sales, and surfacing best-price opportunities with automated updates.',
			contributions: [
				'Facilitated discovery sessions with key stakeholders to understand deal flows.',
				'Designed the system architecture and schema for global auction data.',
				'Developed Laravel 9 server applications integrated with SQL databases.',
				'Built Telegram bot using JavaScript to push daily offer summaries.',
				'Maintained performance, fixed bugs, and trained end-users across web and bot interfaces.'
			],
			tags: ['Laravel 9', 'SQL', 'Telegram Bot', 'Automation']
		},
		{
			name: 'Yayasan Data A Khan Charity Management',
			role: 'Web Application Development',
			brief:
				'Operations console managing beneficiaries, charitable events, and distributed gifts for a nationwide foundation.',
			contributions: [
				'Gathered requirements with program leads to map workflows.',
				'Designed architecture, technology stack, and schema for reliable tracking.',
				'Developed Laravel 9 application with secure role-based modules.',
				'Iterated through performance tuning, bug fixing, and updates.',
				'Produced manuals and facilitated training for staff adoption.'
			],
			tags: ['Laravel 9', 'SQL', 'Nonprofit', 'Reporting']
		},
		{
			name: '15th General Election Coordination Centre (PRU15)',
			role: 'Web Application Development',
			brief:
				'Web platform powering on-ground data collection, analytics, and command dashboards for national election coordination.',
			contributions: [
				'Interviewed field agents to design data capture workflows and offline contingencies.',
				'Planned system architecture and database schema tailored for rapid reporting.',
				'Developed dual Laravel 8 applications with SQL backends to support multiple teams.',
				'Maintained applications through performance refinement and bug fixes.',
				'Created manuals and led training sessions for on-ground users.'
			],
			tags: ['Laravel 8', 'SQL', 'Election Tech', 'Analytics']
		},
		{
			name: 'MIC War Room',
			role: 'Web Application Development',
			brief:
				'Coordination platform for strategic planning, field data capture, and analytics dashboards supporting leadership decisions.',
			contributions: [
				'Partnered with on-ground teams to capture operational needs.',
				'Defined architecture, technology choices, and schema supporting rapid insights.',
				'Developed Laravel 8 applications managing secure data workflows.',
				'Executed performance optimisation and issue resolution cycles.',
				'Delivered documentation and user training for smooth rollout.'
			],
			tags: ['Laravel 8', 'SQL', 'Leadership dashboards', 'Field ops']
		},
		{
			name: 'Aman Rimba Private Estate Revamp',
			role: 'Web Application Development',
			brief:
				'Website overhaul delivering updated design, improved functionality, and responsive experiences for property stakeholders.',
			contributions: [
				'Captured requirements with estate stakeholders to align vision and content.',
				'Planned architecture, selected technologies, and structured the build roadmap.',
				'Developed the new static web experience with streamlined navigation and visuals.',
				'Optimised performance, resolved issues, and ensured accessibility.',
				'Provided documentation and training for ongoing content stewardship.'
			],
			tags: ['Responsive design', 'Static web', 'Content strategy']
		}
	];

	const experience = [
		{
			company: 'AGA Touch (M) Sdn Bhd',
			role: 'Software Developer · IT Technical Department',
			period: 'Sept 2021 → Present',
			highlights: [
				'Migrated legacy Laravel systems from v7 to v10 with improved performance, maintainability, and modular security.',
				'Integrated Supabase for role-based access, multi-factor auth, and live data dashboards served to global stakeholders.',
				'Built data visualizations with Metabase, Google Data Studio, Chart.js, and Highcharts to accelerate decision making.',
				'Delivered mission-critical platforms for elections (BARMM, Maldivian Presidential, PRU15, MIC War Room) and enterprise tender management.',
				'Automated deployments on Shinjiru hosting and Apache, adding monitoring, logging, and error management loops.',
				'Partnered with product and support to deliver cross-functional troubleshooting, documentation, and training.'
			]
		},
		{
			company: 'G3 Global Berhad',
			role: 'Intern · Data Analyst',
			period: 'Mar 2021 → Aug 2021',
			highlights: [
				'Collected, cleaned, and analysed data using Python and SQL to surface insights for internal teams.',
				'Designed interactive dashboards using Metabase and Google Data Studio for executive reporting.',
				'Supported Laravel-based applications with flow planning, database modelling, and Agile collaboration.'
			]
		}
	];

	const toolbelt = [
		'Laravel 8–10',
		'SvelteKit',
		'Tailwind CSS',
		'Supabase',
		'MySQL & SQL',
		'Metabase',
		'Google Data Studio',
		'Chart.js & Highcharts',
		'Cloudflare · Shinjiru',
		'TypeScript',
		'Telegram Bot API',
		'Python'
	];

	const contactLinks = [
		{
			label: 'Phone',
			value: '+60 17-283 4841',
			href: 'tel:+60172834841'
		},
		{
			label: 'Email',
			value: 'atikahsaburi@gmail.com',
			href: 'mailto:atikahsaburi@gmail.com'
		},
		{
			label: 'LinkedIn',
			value: 'linkedin.com/in/atikahsaburi',
			href: 'https://www.linkedin.com/in/atikahsaburi'
		},
		{
			label: 'GitHub',
			value: 'github.com/atikahcodes',
			href: 'https://github.com/atikahcodes'
		}
	];

	const education = [
		{
			program: "Bachelor's Degree · Computer Science (Software Engineering)",
			institution: 'University Malaysia Pahang',
			period: '2017 → 2021',
			location: 'Pahang, Malaysia'
		},
		{
			program: 'Foundation in Biology Science',
			institution: 'Penang Matriculation College',
			period: '2016 → 2017',
			location: 'Penang, Malaysia'
		}
	];
</script>

<div class="relative min-h-screen bg-black text-slate-200">
	<div class="absolute inset-0 -z-10 bg-[radial-gradient(circle_at_top,_rgba(168,85,247,0.18),_transparent_55%)]"></div>
	<div
		class="absolute -top-32 left-1/2 -z-10 h-64 w-[40rem] -translate-x-1/2 rounded-full blur-3xl"
		style="background: radial-gradient(circle, rgba(168, 85, 247, 0.35) 0%, rgba(37, 0, 63, 0) 60%);">
	</div>

	<header class="sticky top-0 z-20 border-b border-purple-500/20 bg-black/70 backdrop-blur">
		<div class="mx-auto flex max-w-6xl items-center justify-between px-6 py-5">
			<a href="#profile" class="text-base font-semibold tracking-[0.25rem] text-purple-400 uppercase"
				>Atikah</a
			>
			<nav class="hidden items-center gap-8 text-sm font-medium text-slate-300 md:flex">
				{#each navLinks as link}
					<a class="transition hover:text-purple-300" href={link.href}>{link.label}</a>
				{/each}
			</nav>
			<a
				class="rounded-full border border-purple-500/60 px-4 py-2 text-xs font-semibold uppercase tracking-widest text-purple-200 shadow-[0_0_25px_rgba(168,85,247,0.25)] transition hover:bg-purple-500/10 hover:text-purple-100"
				href="mailto:atikahsaburi@gmail.com"
				>Book a call</a
			>
		</div>
	</header>

	<main class="relative mx-auto flex max-w-6xl flex-col gap-32 px-6 pb-20 pt-24">
		<section id="profile" class="grid gap-12 lg:grid-cols-[1.1fr_0.9fr]">
			<div class="space-y-8">
				<div class="inline-flex items-center gap-2 rounded-full border border-purple-500/40 px-3 py-1 text-xs uppercase tracking-[0.35em] text-purple-300">
					<span class="h-2 w-2 animate-pulse rounded-full bg-purple-400"></span>
					Open to IT roles
				</div>
				<div class="space-y-4">
					<p class="text-xs font-semibold uppercase tracking-[0.45em] text-purple-300">
						Software Developer · IT Technical Department
					</p>
					<h1 class="text-4xl font-semibold text-white sm:text-5xl md:text-6xl">
						Software developer crafting futuristic, data-rich web experiences.
					</h1>
					<p class="max-w-xl text-base text-slate-300 md:text-lg">
						I’m Nurfatin Atikah Ahmad Subari, a full-stack developer blending Laravel, SvelteKit, Supabase,
						and modern analytics to build platforms that keep civic, election, and enterprise teams in sync.
						I design resilient systems end-to-end — from requirement interviews and architecture to data
						visualisation, launch, and user enablement.
					</p>
				</div>
				<div class="flex flex-wrap gap-3">
					<a
						class="inline-flex items-center justify-center gap-2 rounded-full bg-gradient-to-r from-purple-500 via-purple-400 to-fuchsia-400 px-6 py-3 text-sm font-semibold text-black transition hover:shadow-[0_15px_45px_rgba(168,85,247,0.35)]"
						href="#projects"
					>
						View Projects
					</a>
					<a
						class="inline-flex items-center justify-center gap-2 rounded-full border border-purple-500/40 px-6 py-3 text-sm font-semibold text-purple-200 transition hover:border-purple-400 hover:text-purple-100"
						href="https://www.linkedin.com/in/atikahsaburi"
						target="_blank"
						rel="noreferrer"
					>
						LinkedIn
					</a>
				</div>
				<div class="flex flex-wrap gap-4 text-xs uppercase tracking-[0.35em] text-purple-300">
					<span>Klang · Selangor · Malaysia</span>
					<span>+60 17 283 4841</span>
					<span>atikah-portfolio.pages.dev</span>
				</div>
				<div class="grid gap-4 rounded-3xl border border-purple-500/30 bg-white/5 p-6 backdrop-blur lg:max-w-2xl">
					<div class="flex flex-wrap gap-8">
						{#each highlightStats as stat}
							<div>
								<div class="text-3xl font-semibold text-purple-300">{stat.value}</div>
								<p class="text-xs uppercase tracking-widest text-slate-400">{stat.label}</p>
							</div>
						{/each}
					</div>
					<p class="text-sm text-slate-400">
						Partnering with ministries, election taskforces, and private enterprises across Southeast Asia
						to deliver dependable, insight-driven web tooling.
					</p>
				</div>
			</div>

			<div class="relative">
				<div class="pointer-events-none absolute -top-10 -right-8 hidden md:block">
					<svg
						class="h-32 w-32 orbit-spin text-purple-400/30"
						viewBox="0 0 120 120"
						fill="none"
						stroke="currentColor"
						stroke-width="1.2"
						aria-hidden="true"
					>
						<circle cx="60" cy="60" r="48" stroke-dasharray="6 6" />
						<circle cx="60" cy="60" r="32" stroke-dasharray="4 4" opacity="0.7" />
						<path d="M15 60c12-20 42-48 90-30" opacity="0.6" />
						<path d="M18 82c24 10 60 15 84-18" opacity="0.35" />
						<circle cx="28" cy="46" r="3" fill="currentColor" opacity="0.7" />
						<circle cx="92" cy="70" r="4" fill="currentColor" opacity="0.5" />
						<circle cx="76" cy="28" r="2.5" fill="currentColor" opacity="0.6" />
					</svg>
				</div>
				<div class="absolute -inset-6 -z-10 rounded-[30px] bg-gradient-to-br from-purple-500/25 via-purple-900/10 to-transparent blur-3xl"></div>
				<div class="overflow-hidden rounded-[26px] border border-purple-500/30 bg-black/60 shadow-[0_0_35px_rgba(168,85,247,0.15)]">
					<div class="border-b border-purple-500/20 px-6 py-4">
						<p class="text-xs uppercase tracking-[0.4em] text-purple-200">Current Focus</p>
					</div>
					<div class="space-y-6 px-6 py-8">
						<p class="text-lg text-white">
							Stabilising high-stakes operations with secure dashboards, AI-assisted reporting, and
							real-time collaboration layers that keep distributed teams aligned.
						</p>
						<div class="space-y-4">
							<p class="text-xs uppercase tracking-[0.35em] text-purple-200">Toolbelt</p>
							<div class="flex flex-wrap gap-2">
								{#each toolbelt as tool}
									<span class="rounded-full border border-purple-500/40 px-3 py-1 text-xs text-purple-100">
										{tool}
									</span>
								{/each}
							</div>
						</div>
						<div class="rounded-2xl border border-purple-500/40 bg-purple-950/50 p-4 text-sm text-purple-100">
							<p class="font-medium text-purple-200">Now shipping</p>
							<p class="text-slate-200">
								An election readiness toolkit layering Laravel 10, Supabase, and Highcharts to brief
								leadership with live field intel and AI-assisted summaries.
							</p>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="skills" class="space-y-10">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Professional skills & certifications</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					Grounded in full-stack delivery with a focus on data-rich experiences, automation, and resilient
					deployments that scale with organisational demand.
				</p>
			</div>
			<div class="grid gap-6 md:grid-cols-2">
				{#each professionalSkills as skill}
					<article class="rounded-3xl border border-purple-500/30 bg-white/[0.03] p-6 shadow-[0_0_20px_rgba(168,85,247,0.08)] transition hover:border-purple-400/60 hover:bg-white/[0.05]">
						<h3 class="text-lg font-semibold text-white">{skill.title}</h3>
						<p class="mt-3 text-sm text-slate-300">{skill.description}</p>
					</article>
				{/each}
			</div>
		</section>

		<section id="expertise" class="space-y-12">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Areas of impact</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					I plug into mission-critical squads as a catalyst — aligning the story, the workflows, and the data
					so every release lands with confidence.
				</p>
			</div>
			<div class="grid gap-6 md:grid-cols-3">
				{#each specialties as speciality}
					<article class="group flex h-full flex-col gap-4 rounded-3xl border border-purple-500/30 bg-white/[0.03] p-6 transition hover:border-purple-400/60 hover:bg-white/[0.05]">
						<div class="flex items-center justify-between">
							<h3 class="text-xl font-semibold text-white">{speciality.title}</h3>
							<span class="inline-flex h-10 w-10 items-center justify-center rounded-full bg-purple-500/15 text-purple-200 transition group-hover:bg-purple-500/25 group-hover:text-purple-100">
								✶
							</span>
						</div>
						<p class="flex-1 text-sm text-slate-300">{speciality.description}</p>
						<ul class="space-y-2 text-xs uppercase tracking-[0.35em] text-purple-300">
							{#each speciality.points as point}
								<li>{point}</li>
							{/each}
						</ul>
					</article>
				{/each}
			</div>
		</section>

		<section id="projects" class="relative space-y-10">
			<div class="pointer-events-none absolute -top-16 left-0 hidden md:block">
				<svg
					class="h-28 w-28 float-arc text-purple-400/25"
					viewBox="0 0 120 120"
					fill="none"
					stroke="currentColor"
					stroke-width="1"
					aria-hidden="true"
				>
					<path d="M10 80 Q60 10 110 80" stroke-dasharray="10 8" />
					<path d="M22 92 Q60 40 98 92" opacity="0.5" stroke-dasharray="6 6" />
					<circle cx="34" cy="70" r="3" fill="currentColor" opacity="0.7" />
					<circle cx="86" cy="68" r="4" fill="currentColor" opacity="0.6" />
				</svg>
			</div>
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Highlighted case studies</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					A snapshot of launches where I merged strong full-stack foundations with neon-forward visuals and
					robust data flows.
				</p>
			</div>
			<div class="grid gap-8 md:grid-cols-2">
				{#each projects as project}
					<article class="flex h-full flex-col gap-5 rounded-3xl border border-purple-500/30 bg-black/60 p-6 shadow-[0_0_25px_rgba(168,85,247,0.08)] transition hover:border-purple-300/60 hover:shadow-[0_0_45px_rgba(168,85,247,0.25)]">
						<div class="space-y-2">
							<p class="text-xs uppercase tracking-[0.35em] text-purple-300">{project.role}</p>
							<h3 class="text-xl font-semibold text-white">{project.name}</h3>
						</div>
						<p class="text-sm text-slate-300">{project.brief}</p>
						<ul class="space-y-2 text-sm text-slate-300">
							{#each project.contributions as contribution}
								<li class="flex gap-3">
									<span class="mt-1 h-1.5 w-1.5 flex-shrink-0 rounded-full bg-purple-400"></span>
									<span>{contribution}</span>
								</li>
							{/each}
						</ul>
						<div class="flex flex-wrap gap-2 pt-2">
							{#each project.tags as tag}
								<span class="rounded-full border border-purple-500/40 px-3 py-1 text-xs text-purple-200">
									{tag}
								</span>
							{/each}
						</div>
						{#if project.link}
							<a
								class="inline-flex items-center gap-2 text-sm font-medium text-purple-200 transition hover:text-purple-100"
								href={project.link}
								target="_blank"
								rel="noreferrer"
							>
								<span>Explore case study</span>
								<span aria-hidden="true">↗</span>
							</a>
						{/if}
					</article>
				{/each}
			</div>
		</section>

		<section id="experience" class="space-y-10">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Experience timeline</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					From agency-grade turnarounds to deep product partnerships, I thrive where velocity meets
					refinement.
				</p>
			</div>
			<div class="space-y-8">
				{#each experience as role}
					<article class="relative rounded-3xl border border-purple-500/25 bg-white/[0.04] p-6 shadow-[inset_0_0_0_1px_rgba(168,85,247,0.1)]">
						<div class="flex flex-col gap-3 md:flex-row md:items-start md:justify-between">
							<div>
								<p class="text-xs uppercase tracking-[0.35em] text-purple-300">{role.period}</p>
								<h3 class="text-2xl font-semibold text-white">{role.role}</h3>
								<p class="text-sm text-purple-200">{role.company}</p>
							</div>
							<a
								class="inline-flex items-center gap-2 rounded-full border border-purple-500/30 px-4 py-2 text-xs font-semibold uppercase tracking-[0.3em] text-purple-200 transition hover:border-purple-400 hover:text-purple-100"
								href="mailto:atikahsaburi@gmail.com?subject=Let%E2%80%99s%20talk"
							>
								Connect
							</a>
						</div>
						<ul class="mt-6 space-y-3 text-sm text-slate-300">
							{#each role.highlights as item}
								<li class="flex gap-3">
									<span class="mt-1 h-1.5 w-1.5 flex-shrink-0 rounded-full bg-purple-400"></span>
									<span>{item}</span>
								</li>
							{/each}
						</ul>
					</article>
				{/each}
			</div>
		</section>

		<section id="education" class="space-y-10">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Education</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					Formal training grounded my software engineering practice with computational theory and structured
					problem-solving.
				</p>
			</div>
			<div class="space-y-4">
				{#each education as item}
					<div class="flex flex-col gap-2 rounded-3xl border border-purple-500/30 bg-white/[0.04] p-6 shadow-[0_0_25px_rgba(168,85,247,0.08)] md:flex-row md:items-center md:justify-between">
						<div>
							<p class="text-sm uppercase tracking-[0.35em] text-purple-300">{item.period}</p>
							<p class="text-lg font-semibold text-white">{item.program}</p>
							<p class="text-sm text-purple-200">{item.institution}</p>
						</div>
						<div class="text-sm text-slate-400 md:text-right">
							<span>{item.location}</span>
						</div>
					</div>
				{/each}
			</div>
		</section>

		<section id="contact" class="space-y-10">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<h2 class="text-3xl font-semibold text-white md:text-4xl">Simple contact</h2>
				<p class="max-w-xl text-sm text-slate-400 md:text-right">
					Reach out directly for collaborations, contract roles, or civic tech missions. I respond within a day.
				</p>
			</div>
			<div class="rounded-3xl border border-purple-500/30 bg-white/[0.04] p-6 shadow-[0_0_35px_rgba(168,85,247,0.12)] lg:flex lg:items-center lg:justify-between">
				<div class="space-y-4">
					<p class="text-sm uppercase tracking-[0.35em] text-purple-300">Direct lines</p>
					<ul class="space-y-3 text-sm text-slate-300">
						{#each contactLinks as contact}
							<li>
								<a class="flex gap-4 transition hover:text-purple-200" href={contact.href}>
									<span class="w-28 text-xs uppercase tracking-[0.35em] text-purple-300">{contact.label}</span>
									<span>{contact.value}</span>
								</a>
							</li>
						{/each}
					</ul>
				</div>
				<div class="mt-8 flex flex-col gap-3 lg:mt-0 lg:items-end">
					<a
						class="inline-flex items-center justify-center gap-2 rounded-full bg-gradient-to-r from-purple-500 via-purple-400 to-fuchsia-400 px-6 py-3 text-sm font-semibold text-black transition hover:shadow-[0_15px_45px_rgba(168,85,247,0.35)]"
						href="mailto:atikahsaburi@gmail.com?subject=Let%E2%80%99s%20collaborate"
					>
						Send an email
					</a>
					<p class="text-xs text-slate-400">
						Prefer a call? Use the phone line above — mornings (MYT) are best for quick syncs.
					</p>
				</div>
			</div>
		</section>
	</main>

	<footer class="border-t border-purple-500/20 bg-black/80">
		<div class="mx-auto flex max-w-6xl flex-col gap-3 px-6 py-8 text-sm text-slate-500 md:flex-row md:items-center md:justify-between">
			<p>© {new Date().getFullYear()} Nurfatin Atikah. Crafted with intention.</p>
			<div class="flex gap-6">
				<a class="transition hover:text-purple-200" href="#profile">Profile</a>
				<a class="transition hover:text-purple-200" href="#projects">Work</a>
				<a class="transition hover:text-purple-200" href="#education">Education</a>
				<a class="transition hover:text-purple-200" href="#contact">Contact</a>
			</div>
		</div>
	</footer>
</div>

<style>
	:global(.orbit-spin) {
		animation: orbit-spin 28s linear infinite;
		transform-origin: 50% 50%;
	}

	@keyframes orbit-spin {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(360deg);
		}
	}

	:global(.float-arc) {
		animation: float-arc 12s ease-in-out infinite;
	}

	@keyframes float-arc {
		0%,
		100% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(12px);
		}
	}
</style>
