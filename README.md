# GROUP-BLANK-S-WORKSPACE
Topic: UTM Campus Bus Tracker
<br><br>
🚌 UTM Campus Bus Tracker — 4 Core Deliverables
<br><br>
1 — GPS Live Tracking
Purpose: Real-time location tracking of campus buses with map visualization.
Functionality:Tracks each bus in real time on an interactive campus map using the driver’s phone GPS, with location updates every few seconds.
Key Components:
GPS data polling & cloud sync (Firebase / WebSocket)
Interactive map with moving bus markers (Google Maps API)
Route polyline rendering (visual display of the bus path)
Bus stop markers with stop names
GPS signal weak/offline handling and position smoothing
Historical route playback
<br><br>
2 — Push Notifications for Delays & Cancellations
Purpose: Proactive alerts for bus schedule changes and arrival updates.
Functionality:Alerts subscribed students when their bus is delayed, cancelled, or approaching their selected stop.
Key Components:
Notification subscription system (students select stops/routes to follow)
Delay/cancellation trigger (admin or driver activation)
Push notification engine (Firebase Cloud Messaging)
In-app notification inbox and history
Customizable arrival alerts (configurable distance thresholds)
Do-not-disturb scheduling and priority-based notification tiers
<br><br
3 — Route Recommender (Pin-to-Pin)
Purpose: Smart trip planning based on user start and end points.
Functionality:Students drop pins at their current location and destination. The system recommends the optimal bus route, boarding stop, walking distance, and estimated time of arrival (ETA).
Key Components:
Interactive map with pin-dropping UI
Nearest bus stop detection algorithm
Route matching logic (bus line coverage from origin to destination)
Results screen showing recommended bus, boarding stop, walking distance, and ETA
Multi-route comparison (fastest vs. minimal walking options)
Real-time ETA updates using live bus location data
Transfer route recommendations
<br><br>
4 — Live Bus Occupancy Indicator
Purpose: Transparent visibility into bus crowding levels.
Functionality:Shows how crowded each bus currently is so students can decide whether to wait or take an alternative route.
Key Components:
Driver-side occupancy input (simple 3-level tap: Empty / Moderate / Full)
Occupancy status displayed on the map per bus
Color-coded indicators (green / yellow / red)
Historical occupancy patterns (e.g., "This bus is usually full at 8AM")
Passenger-side occupancy feedback mechanism
Predictive crowding alerts based on historical data
<br><br>
