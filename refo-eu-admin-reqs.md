# Software Requirements Specification (SRS): Refo Consulting Admin Dashboard

## 1. Project Overview
**Objective:** Create a secure, client-side admin dashboard to manage the `data.json` file used by the Refo Consulting EU Funding Calls Tracker. It provides CRUD operations, visibility toggles, and an automated data-gathering interface.

## 2. Technical Architecture
* **State Management:** `localStorage` to handle data across the admin and public pages without a backend.
* **Authentication:** Hardcoded client-side password protection (e.g., simple SHA-256 hash check or simple string match for prototype purposes).
* **Data Export/Import:** Features to upload a `data.json` file, manipulate it, and download the updated version.
* **Scraping Engine:** A module designed to iterate through a list of Source URLs, utilizing a CORS proxy (like `cors-anywhere`) to fetch HTML, with regex/DOM parsing to extract call details.

## 3. User Interface (UI) Modules
### 3.1. Authentication View
* Simple centered login card requiring a password to access the dashboard.

### 3.2. Grants Management Table
* A data grid displaying all current calls.
* **Columns:** ID, Title, Programme, Open Date, Deadline, Status, Actions.
* **Actions:**
  * **Edit/Delete:** Standard CRUD buttons.
  * **Visibility Toggles:** A switch to "Hide/Show" a specific call on the public timeline.
  * **Global Visibility:** A dropdown to hide entire programmes (e.g., "Hide all EIC calls").

### 3.3. Source (Scraping) Manager
* A list of active URLs the system monitors.
* Admin can Add/Edit/Delete source URLs.
* **"Run Scraper" Button:** Triggers the fetch sequence for all active URLs. Displays a progress bar and a log of newly discovered or updated calls.

## 4. Default Source URLs to Monitor
* https://www.eurekanetwork.org/innovation-programmes/
* https://www.smarteureka.com/
* https://www.eurekanetwork.org/programmes-and-calls/innowwide/
* https://www.eurekanetwork.org/programmes-and-calls/eurostars/
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/home
* https://erc.europa.eu/apply-grant
* https://eic.ec.europa.eu/eic-funding-opportunities_en
* https://erasmus-plus.ec.europa.eu/opportunities
* https://cinea.ec.europa.eu/programmes/life_en
* https://digital-strategy.ec.europa.eu/en/activities/digital-programme
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/programmes/horizon
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/
* https://ec.europa.eu/info/funding-tenders/opportunities/data/topic-list.html
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/how-to-participate/participant-register
* https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe_en
* https://horizoneuropencpportal.eu/
* https://erc.europa.eu/
* https://eic.ec.europa.eu/eic-funding-opportunities_en
* https://eic.ec.europa.eu/eic-funding-opportunities/bas_en
* https://eic.ec.europa.eu/eic-funding-opportunities/step-scale_en
* https://erasmus-plus.ec.europa.eu/
* https://cinea.ec.europa.eu/life-calls-proposals-2026_en
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/programmes/life2027
* https://digital-strategy.ec.europa.eu/en/activities/digital-programme
* https://www.eurekanetwork.org/
* https://itea4.org
* https://www.celticnext.eu
* https://www.eurostars-eureka.eu/calls
* https://eurogia.eu
* https://eureka-xecs.com/
* https://www.interstices.eu/en/calls
* https://www.euro-stars.eu/open-calls
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/programmes/digital
* https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/programmes/life2027
* 