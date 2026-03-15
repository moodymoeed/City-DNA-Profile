# City DNA Profile: Socio-Economic Evolution of Turkish Cities (1927-2022)

**Course:** DSA301 - Data Visualization

**Visualization:** Interactive Radial Profile (D3.js)  

## The Research Question
**"How did the Industrial boom of late 20th Century act as a gravity-well for Türkiye's population"**



**Rationale:** Initial data extraction revealed a clear crossover point in the 1980s where manufacturing officially surpassed agriculture as a percentage of GDP. Following this pivot, census data showed explosive, divergent population growth across different cities. I formulated this question to investigate whether this industrial boom merely increased population size, or if it fundamentally altered the socio-economic character (health, education, and industry profile) of these cities.

---

## Task 2: Visualization Sketches
*(Photos of the three hand-drawn sketches are located in the `/sketches` folder).*

1. **The Temporal Snapshot (Bar Chart):** Focuses on the magnitude of population growth pre- and post-1980.
2. **The Economic Gravity Field (Abstract Relational):** Discards a standard timeline to visualize the "pull" of industrialization drawing cities away from their agrarian roots.
3. **The City DNA Profile (Multivariate Radar):** A static conceptualization of the final digital visualization, showing the unique "shape" of each city's infrastructure.

---

## Task 3: Interactive Digital Visualization (D3.js)

### Overview
For the digital implementation, I built an interactive **Radial Profile (Radar Chart)** using D3.js. It allows the user to scrub through nearly a century of data (1927–2022) to watch the "DNA" of six distinct cities evolve in real-time. 

### Design Rationale & Encodings
* **Abstract Intent:** I chose a multivariate radial layout to escape standard X/Y time-series grids. By plotting continuous time on a slider, the visualization emphasizes the *changing shape of a city's identity* rather than just a line trending upwards.
* **Marks:** I used **Closed Polygon (Area) Marks** to represent the total socio-economic footprint of a city in a given year, and **Point Marks (Dots)** to provide interactive precision.
* **Channels:** **Angle/Orientation:** Encodes the categorical identity of the indicator (Health, Education, Industry, Population).
  * **Radial Position (Distance from center):** Encodes the Quantitative Magnitude of the data. 
  * **Color (Hue):** Serves as an Identity Channel to distinguish between cities.

### Application of Gestalt Principles
* **Closure & Enclosure:** By using `d3.curveLinearClosed`, the lines form a complete polygon. The human brain pre-attentively groups these connected points into a single "Object" (the City's DNA), making it easy to compare the bloated shape of a metropolis with the balanced shape of a regional hub.
* **Similarity:** The color of the line exactly matches the color of the checkbox and the hover tooltip, ensuring cognitive alignment without needing extra text labels.
* **Proximity:** Tooltips are anchored dynamically to the user's cursor rather than a static legend, placing the raw data in immediate proximity to the visual mark.

### Key Strengths & Weaknesses
* **Strengths:** Highly effective for multivariate pattern recognition. The animation clearly shows the 1980s "Industrial Pivot" as the exact moment the shapes explode outward, directly answering the research question.
* **Weaknesses:** Radial distortion. Because area scales quadratically, outer values look exponentially larger than inner values, which can slightly distort the visual perception of magnitude compared to a standard bar chart.

### How to Run
Simply open `index.html` in any modern web browser (Chrome, Safari, Firefox). No local server is required. Use the checkboxes to filter cities and the slider to traverse the timeline.