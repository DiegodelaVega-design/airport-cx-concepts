<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Airport CX Concepts & Capabilities</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }

        h1 {
            text-align: center;
            color: #2c3e50;
        }

        #search-bar {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .concept-card {
            background-color: white;
            padding: 20px;
            margin: 10px 0;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .concept-card h2 {
            margin-top: 0;
            color: #2980b9;
        }

        .concept-card p {
            margin: 5px 0;
            color: #2c3e50;
        }

        .capabilities {
            margin-top: 10px;
            list-style-type: none;
            padding-left: 20px;
        }

        .capabilities li {
            margin-bottom: 5px;
        }

        @media (max-width: 768px) {
            body {
                padding: 10px;
            }
        }
    </style>
</head>
<body>

    <h1>Airport CX Concepts & Capabilities</h1>

    <input type="text" id="search-bar" placeholder="Search concepts or capabilities..." onkeyup="filterConcepts()">

    <div id="concept-container">
        <!-- Concept Cards will be injected here dynamically -->
    </div>

    <script>
        // Concepts and capabilities data
        const concepts = [
            {
                name: "Smart Journey Companion",
                description: "A digital assistant app that follows travelers throughout their entire journey.",
                capabilities: [
                    "Tailored updates for each passenger's journey.",
                    "Seamless integration between transport and airport operations.",
                    "Real-time responsiveness and guidance.",
                    "Efficient traveler management through personalized notifications."
                ]
            },
            {
                name: "Biophilic Smart Gateways",
                description: "Gate areas designed with biophilic elements offering personalized relaxation spaces.",
                capabilities: [
                    "Personalized seating areas.",
                    "Quiet zones with natural elements.",
                    "Smart gate management to reduce crowding.",
                    "Biophilic design for enhanced passenger wellbeing."
                ]
            },
            {
                name: "Eco-Connected Transit",
                description: "Sustainable transport options from city centers to terminals.",
                capabilities: [
                    "Luggage-free transit with in-transit check-in.",
                    "Real-time tracking of arrival times and routes.",
                    "Eco-friendly transport reducing environmental impact.",
                    "Carbon footprint tracking for passengers."
                ]
            },
            {
                name: "Wellness Transit Lounge",
                description: "A wellness-focused lounge offering personalized services during layovers.",
                capabilities: [
                    "Sleep pods and meditation rooms on-demand.",
                    "Personalized wellness programs.",
                    "Locally-sourced healthy meal options.",
                    "Biometric wellness scans offering personalized relaxation."
                ]
            },
            {
                name: "Hyper-Personalized Shopping Experience",
                description: "An immersive shopping experience using AR and personalized product recommendations.",
                capabilities: [
                    "AR-enabled virtual product try-ons.",
                    "Personalized product recommendations.",
                    "Gate or destination delivery of purchased items.",
                    "Custom shopping experience based on past behaviors."
                ]
            },
            {
                name: "Dynamic Journey Alerts",
                description: "AI-powered alert system that delivers real-time, relevant information to passengers.",
                capabilities: [
                    "Tailored notifications throughout the journey.",
                    "Personalized updates based on proximity and behavior.",
                    "Real-time traffic, flight, and gate updates.",
                    "Multilingual, customizable alerts."
                ]
            },
            {
                name: "Adaptive Wayfinding Beacons",
                description: "A network of adaptive beacons providing real-time, personalized navigation.",
                capabilities: [
                    "Personalized routes based on location and preferences.",
                    "Proximity-based rerouting during congestion.",
                    "Accessibility-focused navigation support.",
                    "Real-time updates for flight schedules and gate changes."
                ]
            },
            // Add more concepts here as needed...
        ];

        // Function to dynamically render the concept cards
        function renderConcepts() {
            const container = document.getElementById('concept-container');
            container.innerHTML = '';

            concepts.forEach(concept => {
                const card = document.createElement('div');
                card.classList.add('concept-card');

                const title = document.createElement('h2');
                title.textContent = concept.name;
                card.appendChild(title);

                const description = document.createElement('p');
                description.textContent = concept.description;
                card.appendChild(description);

                const capabilitiesList = document.createElement('ul');
                capabilitiesList.classList.add('capabilities');
                concept.capabilities.forEach(capability => {
                    const listItem = document.createElement('li');
                    listItem.textContent = capability;
                    capabilitiesList.appendChild(listItem);
                });
                card.appendChild(capabilitiesList);

                container.appendChild(card);
            });
        }

        // Function to filter concepts based on search input
        function filterConcepts() {
            const query = document.getElementById('search-bar').value.toLowerCase();
            const filteredConcepts = concepts.filter(concept => {
                return (
                    concept.name.toLowerCase().includes(query) ||
                    concept.description.toLowerCase().includes(query) ||
                    concept.capabilities.some(capability => capability.toLowerCase().includes(query))
                );
            });

            renderFilteredConcepts(filteredConcepts);
        }

        // Render the filtered concepts dynamically
        function renderFilteredConcepts(filteredConcepts) {
            const container = document.getElementById('concept-container');
            container.innerHTML = '';

            filteredConcepts.forEach(concept => {
                const card = document.createElement('div');
                card.classList.add('concept-card');

                const title = document.createElement('h2');
                title.textContent = concept.name;
                card.appendChild(title);

                const description = document.createElement('p');
                description.textContent = concept.description;
                card.appendChild(description);

                const capabilitiesList = document.createElement('ul');
                capabilitiesList.classList.add('capabilities');
                concept.capabilities.forEach(capability => {
                    const listItem = document.createElement('li');
                    listItem.textContent = capability;
                    capabilitiesList.appendChild(listItem);
                });
                card.appendChild(capabilitiesList);

                container.appendChild(card);
            });
        }

        // Render concepts initially
        renderConcepts();
    </script>
</body>
</html>
