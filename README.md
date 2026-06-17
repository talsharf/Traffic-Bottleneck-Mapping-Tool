# Local Traffic Bottleneck Mapping Tool

A modern, interactive web application to map and analyze local traffic patterns around a specific bottleneck area or street intersection. 

This tool helps urban planners, researchers, or curious commuters study how routes converge on a target location, which directions experience the most delays, and which specific paths pass directly through a chosen bottleneck.

---

## 🚀 What You Can Do With This Application

*   **Select a Target Location:** Enter any street intersection or address as your "target bottleneck." The map centers on this area, making it the focal point of your traffic study.
*   **Generate commuting paths from all directions:** 
    *   Set up multiple circular zones (tiers) around your target to test short, medium, and long commutes.
    *   Symmetrically distribute starting points around each circle to simulate drivers coming in from North, South, East, West, and everywhere in between.
*   **Analyze Different Times of Day:** Toggle morning, midday, evening, or night time blocks (or add your own custom hour) to see how traffic flow and travel times fluctuate throughout the day.
*   **Run Simulations in Sandbox or Live Mode:**
    *   **Google Maps Mode (Live Data):** Enter a Google Maps API Key to fetch real-world routes and live travel times to capture true traffic conditions.
    *   **Sandbox Simulator (For Testing Only):** Runs a free, offline simulation with mock routes. This is only for testing the app's features and does not use real traffic data.
*   **Interactive Route Report:** The system displays an interactive report with a list of all routes that it checked and whether they passed through the bottleneck location or not. You can easily filter the list and examine individual routes on the map to see exactly where they started and ended.
*   **Visualize Routes on an Interactive Map:**
    *   Select any route from your logs to display its detailed road path on the map.
    *   Show starting (red circle) and ending (green circle) markers, along with direction arrows.
    *   Toggle **All** routes to overlay all simulated paths at once.
    *   Toggle **Sampled** straight lines to draw clean green lines connecting start and end points for simplified visual mapping.
*   **Store and Export Logs:** All run results are saved directly to a database on your computer. You can search, filter by whether they pass the bottleneck, review turn-by-turn driving directions, and export everything to a CSV file for use in Excel or Google Sheets.

---

## 🛠️ How to Get Started

### 1. Launch the Server
To run the application, launch the local HTTP server included in the project. Open your terminal in the project directory and run:
```bash
node server.js
```
This will start the server on your machine.

### 2. Open the Application
Open your web browser and navigate to:
```
http://localhost:8080
```

---

## 📖 How to Use the Tool

1.  **Choose Your Engine Mode:** At the top of the left Control Panel, select **Sandbox** to try it out offline, or click **Google Maps** (and expand `⚙️ Configure Key` to input your API key).
2.  **Set the Target Address:** Enter the intersection you want to study (e.g. `Boulevard Saint-Joseph & Rue de Lanaudière, Montréal, QC`).
3.  **Adjust the Search Zones (Optional):**
    *   **Start:** The radius of the innermost circle in meters.
    *   **Step:** The multiplication factor for outer circles (e.g., 2.0 doubles the radius for each consecutive circle).
    *   **Circles:** The number of concentric circles to generate.
    *   **Symmetry Points:** How many starting locations to generate around each circle.
4.  **Select Time Blocks:** Check the hours you want to query. You can add custom times (like `09:30` or `15:15`) using the text box under the grid.
5.  **Click "Start Run":** The tool will start running queries. You'll see a progress bar and status updates. You can hit **Halt** at any time to safely stop the run and keep the data collected so far.
6.  **Filter & Review Results:**
    *   Use the dropdown filters on the **Routes** table to view only routes that pass or do not pass the target bottleneck, or filter by time of day.
    *   Click on a row in the table to display its route on the map.
    *   Click the `...` button at the end of any row to open the **Route Details** panel. This shows a clean start/end address (showing only house number and street name) and detailed turn-by-turn directions.
7.  **Save Your Data:** Click **Export CSV** at the bottom of the sidebar to download your database logs into a spreadsheet. If you want to start fresh, click the red **Clear DB** button.
