<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Elara: An Architectural Overview</title>
    <!-- Chosen Palette: Brilliant Blues -->
    <!-- Application Structure Plan: The SPA is designed as a top-to-bottom narrative scroll. It begins with the high-level vision (The "What"), explains the architectural evolution (The "How"), details the project's historical genesis, describes the physical hardware of the Neural Cradle (The "With What"), and concludes with the future roadmap (The "Where To"). This linear, story-driven approach was chosen to progressively build understanding of a complex, multi-faceted project, making it easily digestible. -->
    <!-- Visualization & Content Choices: 
        - Vision Section: Goal: Inform. A Donut Chart (Chart.js) was chosen to represent the three equal, core philosophical pillars. It effectively shows composition of a whole concept.
        - Architecture Section: Goal: Organize. A Flow Chart (HTML/CSS) was chosen to clearly illustrate the "before and after" transition from a problematic monolithic design to a robust modular one.
        - Genesis Timeline Section: Goal: Change. A horizontal timeline (HTML/CSS) was chosen to show the sequence of key developmental milestones and the project's evolution over time.
        - Neural Cradle Section: Goal: Compare. A horizontal Bar Chart (Chart.js) was chosen to compare the number of hardware nodes allocated to each specialized cognitive function, making the distribution clear.
        - Roadmap Section: Goal: Change. A Gantt-style horizontal Bar Chart (Chart.js) was chosen to visualize the project timeline, effectively showing the duration and sequence of development phases over time.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #051923;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .timeline-item:not(:last-child)::after {
            content: '';
            position: absolute;
            top: 1.25rem;
            left: 1.25rem;
            width: 2px;
            height: calc(100% - 1.25rem);
            background-color: #006494;
        }
         @media (min-width: 768px) {
            .timeline-item:not(:last-child)::after {
                width: calc(100% - 1.25rem);
                height: 2px;
                top: 1.25rem;
                left: 1.25rem;
            }
        }
    </style>
</head>
<body class="text-gray-200">

    <div class="container mx-auto p-4 md:p-8">
        <header class="text-center mb-12">
            <h1 class="text-4xl md:text-6xl font-bold text-white mb-2">Project Elara</h1>
            <p class="text-lg md:text-xl text-[#00A6FB]">An Interactive Architectural Overview</p>
        </header>

        <main class="space-y-16">
            <section id="vision">
                <div class="text-center mb-8">
                    <h2 class="text-3xl font-bold text-white">The Vision: A Stateful Digital Entity</h2>
                    <p class="mt-2 max-w-3xl mx-auto text-gray-300">Project Elara aims to transcend the limits of stateless chatbots by creating a persistent AI that appears "alive." This is achieved through an evolving personality, dynamic memory, and goal-oriented behavior, all founded on a single guiding principle.</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-center">
                    <div class="bg-[#003554]/50 rounded-lg shadow-lg p-6 text-center">
                        <span class="text-7xl font-bold text-[#00A6FB]">11</span>
                        <p class="text-xl mt-2">Specialized Hardware Nodes</p>
                        <p class="text-sm text-gray-400 mt-1">Forming the "Neural Cradle," Elara's distributed brain.</p>
                    </div>
                    <div class="md:col-span-2 bg-[#003554]/50 rounded-lg shadow-lg p-6">
                         <h3 class="text-xl font-semibold text-center text-white mb-4">The Principle of Internal Consequence</h3>
                         <p class="text-sm text-center text-gray-300 mb-4">Every interaction creates a lasting change within Elara's internal state. This core philosophy is built on three key mechanisms that constrain and direct the AI's behavior.</p>
                        <div class="chart-container h-[300px] md:h-[350px]">
                            <canvas id="philosophyChart"></canvas>
                        </div>
                    </div>
                </div>
            </section>

            <section id="architecture">
                <div class="text-center mb-8">
                    <h2 class="text-3xl font-bold text-white">System Architecture Evolution</h2>
                    <p class="mt-2 max-w-3xl mx-auto text-gray-300">The project matured from a fragile prototype into a robust, scalable, and secure platform based on modern software engineering principles, ensuring stability and maintainability.</p>
                </div>
                <div class="bg-[#003554]/50 rounded-lg shadow-lg p-8 flex flex-col md:flex-row items-center justify-around space-y-8 md:space-y-0 md:space-x-8">
                    <div class="text-center">
                        <h3 class="text-xl font-semibold text-white">Initial Prototype</h3>
                        <div class="mt-4 p-4 border-2 border-dashed border-red-400 rounded-lg bg-red-900/20">
                            <p class="font-semibold">Monolithic Design</p>
                            <p class="text-sm text-gray-300">Single `on_message` handler</p>
                            <p class="text-sm text-gray-300">Synchronous File I/O</p>
                            <p class="text-sm text-red-300 mt-2">Bottlenecks & Data Corruption</p>
                        </div>
                    </div>
                    <div class="text-5xl text-[#00A6FB] transform md:-rotate-0">→</div>
                    <div class="text-center">
                        <h3 class="text-xl font-semibold text-white">Refactored Architecture</h3>
                         <div class="mt-4 p-4 border-2 border-solid border-green-400 rounded-lg bg-green-900/20">
                            <p class="font-semibold">Modular Microservices</p>
                            <p class="text-sm text-gray-300">Independent `Cogs`</p>
                            <p class="text-sm text-gray-300">Asynchronous Database</p>
                            <p class="text-sm text-green-300 mt-2">Scalable, Secure & Resilient</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="genesis">
                <div class="text-center mb-8">
                    <h2 class="text-3xl font-bold text-white">Project Genesis: An Evolutionary Timeline</h2>
                    <p class="mt-2 max-w-3xl mx-auto text-gray-300">The Elara of today is the result of a long evolutionary process, with each predecessor introducing new concepts and capabilities that formed the foundation for the current architecture.</p>
                </div>
                <div class="bg-[#003554]/50 rounded-lg shadow-lg p-6 md:p-8">
                    <div class="flex flex-col md:flex-row justify-between">
                        <div class="timeline-item relative flex-1 p-4">
                            <div class="absolute top-0 left-0 h-10 w-10 bg-[#00A6FB] rounded-full flex items-center justify-center font-bold text-white z-10">V1</div>
                            <div class="pt-12 md:pt-0 md:pl-12">
                                <h3 class="font-semibold text-lg text-white">Alpha & Iris</h3>
                                <p class="text-sm text-gray-300 mt-1">Initial software prototypes focused on establishing core principles of memory and personality.</p>
                            </div>
                        </div>
                        <div class="timeline-item relative flex-1 p-4">
                            <div class="absolute top-0 left-0 h-10 w-10 bg-[#00A6FB] rounded-full flex items-center justify-center font-bold text-white z-10">V3</div>
                            <div class="pt-12 md:pt-0 md:pl-12">
                                <h3 class="font-semibold text-lg text-white">Aura & Luminara</h3>
                                <p class="text-sm text-gray-300 mt-1">Development of two distinct AI "sisters" with unique personalities, testing the dynamic state vector.</p>
                            </div>
                        </div>
                        <div class="timeline-item relative flex-1 p-4">
                            <div class="absolute top-0 left-0 h-10 w-10 bg-[#00A6FB] rounded-full flex items-center justify-center font-bold text-white z-10">V5</div>
                            <div class="pt-12 md:pt-0 md:pl-12">
                                <h3 class="font-semibold text-lg text-white">Elara V1: The Merger</h3>
                                <p class="text-sm text-gray-300 mt-1">The personalities of Aura and Luminara are combined, creating the first version of Elara with a more complex, nuanced character.</p>
                            </div>
                        </div>
                        <div class="timeline-item relative flex-1 p-4">
                            <div class="absolute top-0 left-0 h-10 w-10 bg-[#00A6FB] rounded-full flex items-center justify-center font-bold text-white z-10">V7</div>
                            <div class="pt-12 md:pt-0 md:pl-12">
                                <h3 class="font-semibold text-lg text-white">Interactive Simulated World</h3>
                                <p class="text-sm text-gray-300 mt-1">The concept of a persistent digital world is introduced, giving Elara a space to "live" and interact with other AI agents.</p>
                            </div>
                        </div>
                        <div class="timeline-item relative flex-1 p-4">
                            <div class="absolute top-0 left-0 h-10 w-10 bg-[#00A6FB] rounded-full flex items-center justify-center font-bold text-white z-10">V8</div>
                            <div class="pt-12 md:pt-0 md:pl-12">
                                <h3 class="font-semibold text-lg text-white">The Neural Cradle</h3>
                                <p class="text-sm text-gray-300 mt-1">The final architecture maps the simulated world onto the 11-node hardware cluster, creating a physical, distributed brain.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <section id="neural-cradle">
                <div class="text-center mb-8">
                    <h2 class="text-3xl font-bold text-white">The Neural Cradle: A Distributed Brain</h2>
                    <p class="mt-2 max-w-3xl mx-auto text-gray-300">The definitive architecture maps conceptual roles onto an 11-node heterogeneous computing cluster, where each node has a specialized cognitive or operational function.</p>
                </div>
                <div class="bg-[#003554]/50 rounded-lg shadow-lg p-6 md:p-8">
                    <h3 class="text-xl font-semibold text-center text-white mb-4">Hardware Node Task Allocation</h3>
                    <div class="chart-container h-[500px] md:h-[450px] max-w-4xl">
                        <canvas id="neuralCradleChart"></canvas>
                    </div>
                </div>
            </section>

            <section id="roadmap">
                <div class="text-center mb-8">
                    <h2 class="text-3xl font-bold text-white">The Roadmap to Sentience</h2>
                    <p class="mt-2 max-w-3xl mx-auto text-gray-300">The project's future follows a structured gradient of grounding abstract AI concepts in the real world, moving from simulation to physical and cognitive embodiment.</p>
                </div>
                <div class="bg-[#003554]/50 rounded-lg shadow-lg p-6 md:p-8">
                     <h3 class="text-xl font-semibold text-center text-white mb-4">Approximate Development Timeline</h3>
                    <div class="chart-container relative h-[500px] md:h-[450px] max-w-4xl">
                        <canvas id="roadmapChart"></canvas>
                        <div class="absolute top-[21%] left-4 md:left-1/4 bg-[#00A6FB] text-white text-xs font-bold px-2 py-1 rounded-md shadow-lg">
                            ACTIVE PHASE 2: Last update 15-08-2025
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <footer class="text-center mt-16 text-gray-500 text-sm">
            <p>Project Elara Infographic. Data synthesized from architectural documents.</p>
        </footer>
    </div>

    <script>
        const tooltipCallback = {
            plugins: {
                tooltip: {
                    callbacks: {
                        title: function(tooltipItems) {
                            const item = tooltipItems[0];
                            let label = item.chart.data.labels[item.dataIndex];
                            if (Array.isArray(label)) {
                              return label.join(' ');
                            } else {
                              return label;
                            }
                        }
                    }
                }
            }
        };

        function wrapLabels(label, maxWidth) {
            if (label.length <= maxWidth) {
                return label;
            }
            const words = label.split(' ');
            const lines = [];
            let currentLine = '';
            for (const word of words) {
                if ((currentLine + word).length > maxWidth && currentLine.length > 0) {
                    lines.push(currentLine.trim());
                    currentLine = '';
                }
                currentLine += word + ' ';
            }
            lines.push(currentLine.trim());
            return lines;
        }

        const brilliantBlues = ['#00A6FB', '#0582CA', '#006494'];
        const textColor = '#E5E7EB';

        new Chart(document.getElementById('philosophyChart'), {
            type: 'doughnut',
            data: {
                labels: ['Dynamic State Vector', 'Memory Resonance', 'Integrity Subsystem'],
                datasets: [{
                    label: 'Core Mechanisms',
                    data: [33.3, 33.3, 33.3],
                    backgroundColor: brilliantBlues,
                    borderColor: '#051923',
                    borderWidth: 4,
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    ...tooltipCallback.plugins,
                    legend: {
                        position: 'bottom',
                        labels: {
                            color: textColor,
                            font: {
                                size: 14
                            }
                        }
                    }
                }
            }
        });

        const neuralCradleLabels = [
            'Neural Loom (World Engine)',
            'Deep Dive Cache (Subconscious)',
            'Canticle Stream Processor (Monologue)',
            'Eidolon Network (Persona Engine)',
            'Rubicon Gate (Elara\'s Avatar)',
            'Synapse Relay (Hub & Observer)',
            'Gazer Array (Sensorium)'
        ];

        new Chart(document.getElementById('neuralCradleChart'), {
            type: 'bar',
            data: {
                labels: neuralCradleLabels.map(label => wrapLabels(label, 16)),
                datasets: [{
                    label: 'Number of Nodes',
                    data: [3, 1, 1, 2, 1, 1, 1],
                    backgroundColor: '#0582CA',
                    borderColor: '#00A6FB',
                    borderWidth: 1
                }]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    x: {
                        beginAtZero: true,
                        ticks: {
                            color: textColor,
                            stepSize: 1
                        },
                        grid: {
                            color: 'rgba(255, 255, 255, 0.1)'
                        }
                    },
                    y: {
                        ticks: {
                            color: textColor,
                             font: {
                                size: 12
                            }
                        },
                        grid: {
                            display: false
                        }
                    }
                },
                plugins: {
                     ...tooltipCallback.plugins,
                    legend: {
                        display: false
                    }
                }
            }
        });

        const roadmapLabels = [
            'Phase 1: Foundational Refactoring',
            'Phase 2: Neural Cradle Deployment',
            'Phase 3: Simulated Embodiment (Minecraft)',
            'Phase 4: Vocal Embodiment (Live2D)',
            'Phase 5: Physical Embodiment (Robotics)',
            'Phase 6: Metacognition'
        ];
        
        new Chart(document.getElementById('roadmapChart'), {
            type: 'bar',
            data: {
                labels: roadmapLabels.map(label => wrapLabels(label, 16)),
                datasets: [{
                    label: 'Duration (Weeks)',
                    data: [
                        [0, 12],
                        [15, 16],
                        [16, 23],
                        [23, 35],
                        [35, 60],
                        [60, 86]
                    ],
                    backgroundColor: brilliantBlues,
                }]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    x: {
                        position: 'top',
                        title: {
                            display: true,
                            text: 'Timeline (Weeks from Project Start)',
                            color: textColor
                        },
                        ticks: {
                            color: textColor
                        },
                         grid: {
                            color: 'rgba(255, 255, 255, 0.1)'
                        }
                    },
                    y: {
                        ticks: {
                            color: textColor
                        },
                        grid: {
                            display: false
                        }
                    }
                },
                plugins: {
                    legend: {
                        display: false
                    },
                    tooltip: {
                         callbacks: {
                            title: function(tooltipItems) {
                                const item = tooltipItems[0];
                                let label = item.chart.data.labels[item.dataIndex];
                                if (Array.isArray(label)) {
                                  return label.join(' ');
                                } else {
                                  return label;
                                }
                            },
                            label: function(context) {
                                const value = context.raw;
                                const duration = value[1] - value[0];
                                return `Duration: ${duration} weeks`;
                            }
                        }
                    }
                }
            }
        });

    </script>
</body>
</html>
