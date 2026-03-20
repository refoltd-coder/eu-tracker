# Software Requirements Specification (SRS): Refo Consulting EU Funding Calls Tracker

## 1. Project Overview
**Project Name:** Refo Consulting EU Funding Calls Tracker
**Deployment Target:** Single-Page Application (SPA) integrated into `https://refo.com.tr/`
**Objective:** To provide a visual, interactive, and easily deployable web interface for tracking active and upcoming European funding calls. The tool will use a Gantt-style timeline to display grant lifecycles without requiring a backend database.

## 2. Technical Architecture
* **Frontend:** Vanilla JavaScript (ES6+), HTML5, CSS3.
* **Styling:** CSS variables mapped to Refo Consulting's brand identity (clean corporate styling, integrating existing brand colors from refo.com.tr).
* **Timeline Engine:** `Vis.js Timeline` or `Frappe Gantt` for rendering the timeline visualization.
* **Data Layer:** A local, static `data.json` file. All operations (search, filter, render) will be performed client-side.

## 3. User Interface (UI) Requirements


### 3.1. Top Navigation & Control Bar (Sticky)
* **Branding:** Refo Consulting logo embedded in the top left.
* **Global Search:** Text input field filtering by Call Title, Reference ID, or keyword.
* **Filters:**
  * **Programme Dropdown:** Horizon Europe, Eureka, EIC, Erasmus+, Digital Europe, LIFE, etc.
  * **Status Dropdown:** Active, Upcoming, Closed.
* **View Controls:** Timeline zoom controls (Months, Quarters, Years).

### 3.2. Main Timeline Area (Gantt Chart)
* **Layout:** Takes up ~80% of the viewport height. 
* **Y-Axis (Left):** Grouped by Programme and Sub-pillar (e.g., *Eureka Clusters -> CELTIC-NEXT*).
* **X-Axis (Top):** Continuous chronological timeline.
* **Data Items (Bars):**
  * Horizontal bars spanning from the call's `openDate` to `deadline`.
  * **Color Coding:** Distinct colors for different overarching programmes.
  * **Interactivity:** Hovering displays a tooltip (Call Name, Deadline, Budget). Clicking opens the Details Modal.

### 3.3. Call Details Modal (Overlay)
* **Trigger:** Clicking a timeline bar.
* **Content Displayed:**
  * Programme Name & Reference ID.
  * Call Title.
  * Exact Opening Date and Deadline (with days remaining).
  * Budget and Funding Rate.
  * Brief Description.
* **Call to Action:** "Go to Official Call Page" (Opens URL in a new tab).
* **Behavior:** Click outside to close, or click top-right 'X'.

## 4. Data Schema (`data.json`)
The application will fetch and parse an array of JSON objects structured as follows:
```json
[
  {
    "id": "ERASMUS-SPORT-2026-SCP",
    "title": "Cooperation Partnerships in Sport",
    "programme": "Erasmus+",
    "pillar": "Sport",
    "openDate": "2025-11-01",
    "deadline": "2026-03-05",
    "budget": "Varies",
    "description": "Support for transnational projects aiming to develop, transfer and implement innovative practices in sport.",
    "url": "[https://erasmus-plus.ec.europa.eu/](https://erasmus-plus.ec.europa.eu/)",
    "status": "active"
  }
]