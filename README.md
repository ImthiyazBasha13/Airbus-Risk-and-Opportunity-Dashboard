Airbus Opportunity Framework Application
1. Introduction
Welcome to the Airbus Opportunity Framework, a web-based tool designed to streamline the process of identifying, validating, and evaluating business opportunities. This application provides a structured, three-part workflow that guides users from initial brainstorming to quantitative analysis, helping to make informed, data-driven decisions.

Built with HTML, CSS, and vanilla JavaScript, the tool is designed to be modular and easily customizable, making it a perfect fit for strategic planning and analysis.

2. Features
The application is divided into three main sections, each corresponding to a key stage in the opportunity assessment process.

a. Identifying Right Questions (cluster.html)
This interactive visualization helps users explore key strategic areas and the critical questions associated with them.

Interactive Sunburst Chart: A multi-layered chart that organizes opportunity areas into three main categories: Team, Organisation, and Environment.

Drill-Down Details: Clicking on any segment of the chart reveals a popup with detailed questions and considerations related to that specific area, prompting deeper strategic thinking.

b. Identification and Validation of Opportunities (card.html)
This section provides a dynamic interface for creating and managing detailed profiles for each business opportunity.

Dynamic Opportunity Cards: Users can add, edit, and delete cards, each representing a unique opportunity.

Customizable Attributes: Each card includes fields for a name, category, type, risk, and scalability.

Quantitative Scaling: A comprehensive set of sliders allows users to score each opportunity on a scale of 1-10 across various metrics like Impact, Feasibility, and Strategic Benefit.

Persistent Storage: All data entered is saved in the browser's localStorage, ensuring that work is not lost between sessions.

c. Evaluation of Opportunities (map.html)
This is the final stage, where all defined opportunities are plotted on an interactive heatmap for comparative analysis.

Interactive Heatmap: A 10x10 grid that visually represents the value of different combinations of metrics. The color of each cell (red, yellow, green) indicates the strength of the opportunity.

Dynamic Axes: The X and Y axes of the heatmap can be changed on the fly using dropdown menus. These menus are automatically populated with the scaling factors defined on the "Opportunity Card" page.

Data Visualization: Each opportunity is plotted on the map as a distinct point, allowing for an at-a-glance comparison of its position relative to others.

Descriptive Labels: The axes are labeled with both qualitative descriptors (e.g., 'Very Low', 'Medium', 'High') and numerical values to enhance readability.

3. How It Works
The three sections of the application are seamlessly connected through the use of the browser's localStorage.

Defining the Metrics: The SCALERS array in card.js is the single source of truth for all quantitative metrics. When this page loads, it saves this array to localStorage.

Creating the Data: On the card.html page, users create opportunity cards. Every time a card is saved, the entire collection of opportunities is stored as a JSON object in localStorage.

Visualizing the Data: When the map.html page loads, it reads both the list of available metrics and the saved opportunity data from localStorage. It then uses this information to dynamically build the dropdown menus and plot the opportunities on the heatmap.

This architecture ensures that any changes made to the scaling factors on the card page are instantly reflected in the evaluation heatmap.

4. File Structure
The project is organized into a straightforward directory structure:

dashboard/
├── Pages/
│   ├── card.html
│   ├── card.js
│   ├── cluster.html
│   ├── cluster.js
│   ├── index.html
│   ├── map.html
│   └── map.js
├── Style/
│   └── style.css
└── app.js

5. How to Use
Start on the Home Page (index.html): This page serves as the main navigation hub.

Explore Questions (cluster.html): Use the sunburst chart to brainstorm and understand the key areas of focus.

Define Opportunities (card.html): Create cards for each opportunity, fill in the attributes, and use the sliders to assign scores.

Evaluate and Compare (map.html): Use the heatmap to visually analyze your opportunities. Change the X and Y axes to compare them across different dimensions.

6. Customization
The application is designed for easy customization. To change the attributes or scaling factors used across the tool, you only need to edit the arrays at the top of the card.js file.

For example, to add a new slider for "Market Size," simply add a new entry to the SCALERS array:

const SCALERS = [
    // ... existing scalers
    { label: 'Market Size', key: 'marketSize' }
];

The application will automatically add this new slider to the opportunity cards and include "Market Size" as an option in the heatmap's axis selection dropdowns.
