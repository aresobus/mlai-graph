
# Media Central Visual Detection Frontend

## Overview
This repository contains the frontend code for the visual detection portion of Media Central, specifically designed to interface with a backend video model for AI-driven content analysis. This frontend visualizes AI detection results for various media content, such as nudity, sexual activity, and other explicit content, which assists in moderating and filtering content effectively.

## Description
The core functionality of this frontend is to convert raw detection data provided by the AI model into a user-friendly visual format using Plotly.js. This conversion involves:
- Parsing time-coded detection data from the backend.
- Displaying this data on a dynamic, interactive scatter plot.
- Allowing users to filter and view specific data points based on their severity or type.

### Key Components
1. **Time Conversion (`sec2timestamp` Function):**
   Converts raw second-based timestamps into a full timestamp format `YYYY-MM-DD HH:MM:SS.sss`, compatible with Plotly for precise plotting on a timeline.

2. **Data Structure (`dataJSON`):**
   Holds the AI model's output as a JSON object. Each category (e.g., Nudity, Sexual Activity) is associated with time-coded detection values indicating the confidence level (%) detected at those specific times.

3. **Plotly Graph Construction:**
   - **Data Preparation:**
     Converts `dataJSON` into Plotly-readable format, creating individual scatter plot data objects for different detected categories.
   - **Graph Styling:**
     Configures visual aspects of the graph such as colors, axis formats, and hover information using a predefined color palette and layout settings.
   - **Interactive Elements:**
     Implements interactive graph features like zoom, filter sliders, custom tooltips, and a dynamic legend that allows users to toggle visibility of data categories.

4. **Interactive UI Elements:**
   - **Legend Customization:**
     Dynamically generates legend buttons based on the categories present in `dataJSON`, allowing users to filter visible data on the graph.
   - **Threshold Slider:**
     Provides a slider for users to set a lower threshold on the detection confidence, updating the graph to only show data points above the selected value.

## Setup
To set up and run this project locally:
1. Clone the repository to your local machine.
2. Ensure you have `Plotly.js` installed, or include it via a CDN in your HTML.
3. Open the `index.html` file in a web browser to view the graph.

## Integration with AI Model
This frontend is designed to work seamlessly with a backend AI model that analyzes video content and sends detection results in real-time. The integration assumes a WebSocket or REST API connection that continuously feeds detection data into `dataJSON`.

## Contributing
Contributions to enhance or expand the functionality of this frontend are welcome. Please follow standard GitHub pull request procedures to submit your contributions.

## License
This project is licensed under the MIT License. 

## Author
Alex Lebedyev (oleksandr.lebedyev@nbcuni.com)