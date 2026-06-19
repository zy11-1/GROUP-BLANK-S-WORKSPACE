# GROUP-BLANK's-WORKSPACE
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
<br><br>
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
<br><br><br><br>
Subsystem 1: GPS Live Tracking

UC001 - View Live Bus Location (Student)

Student opens Live Tracking → System retrieves GPS coordinates → Displays bus locations on map


UC002 - Update Bus GPS Location (Driver)

GPS device detects location → System retrieves coordinates → Updates GPS database


UC003 - View Estimated Arrival Time (ETA) (Student)

Student selects bus stop/route → System calculates ETA → Displays arrival time

<br><br><br><br>
Subsystem 2: Route Recommender (Pin-to-Pin)

UC004 - Plan Pin-to-Pin Route (Student)

Student selects origin & destination → System retrieves stops & routes → Displays recommended route


UC005 - View Recommended Bus Route (Student)

Student selects recommended route → System displays route path, ETA, and walking distance


UC006 - Manage Bus Stop Information (Admin)

Admin selects stop to update → Edits details → System validates and stores updates


UC007 - View Bus Stop Details (Student)

Student selects bus stop → System displays name, routes, ETA

<br><br><br><br>
Subsystem 3: Push Notifications for Delays & Cancellations

UC008 - Subscribe to Bus Route Notifications (Student)

Student opens Notification Settings → Selects routes/stops → System saves subscription


UC009 - Receive Delay or Cancellation Notification (Student / Admin)

Admin/Driver triggers event → NotificationService queries subscribers → FCM sends push notifications


UC009B - View Notification Inbox (Student)

Student opens Notification Inbox → System fetches history → Displays chronological list

<br><br><br><br>
Subsystem 4: Live Bus Occupancy Indicator

UC010 - View Live Bus Occupancy Status (Student)

Student selects Bus Occupancy → System retrieves data → Displays color-coded status (Green/Yellow/Red)


UC011 - Update Bus Occupancy Status (Driver)

Driver selects occupancy level (Empty/Moderate/Full) → System updates database


UC012 - View Predicted Bus Crowd Level (Student)

Student selects route/stop → System analyzes trends → Displays predicted crowd level

<br><br><br><br>
Summary
<br><br><br><br>
Subsystem	Use Cases
GPS Live Tracking	UC001, UC002, UC003<br><br><br><br>
Route Recommender	UC004, UC005, UC006, UC007<br><br><br><br>
Push Notifications	UC008, UC009, UC009B<br><br><br><br>
Live Occupancy Indicator	UC010, UC011, UC012<br><br><br><br>
Total	12 use cases (UC001 – UC012)<br><br><br><br>

Actor Summary：<br><br><br><br>

Student (10 use cases): UC001, UC003, UC004, UC005, UC007, UC008, UC009, UC009B, UC010, UC012<br><br><br><br>

Driver (2 use cases): UC002, UC011<br><br><br><br>

Admin (2 use cases): UC006, UC009<br><br><br><br>


Use Case Coverage in Prototype

UC001: Student Live Map page ✅

UC002: Driver Dashboard → Update GPS ✅

UC003: Student Live Map (ETA countdown) ✅

UC004: Student Route Planner → Find Best Route ✅

UC005: Recommended Route page ✅

UC006: Admin Dashboard → Manage Stops ✅

UC007: Stop Details page ✅

UC008: Student Alerts → Subscription toggles ✅

UC009: Driver → Send Alert → Student Inbox updates ✅

UC009B: Student Alerts → Notification Inbox ✅

UC010: Student Occupancy page ✅

UC011: Driver Dashboard → Update Occupancy ✅

UC012: Student Occupancy → AI Insight card ✅
