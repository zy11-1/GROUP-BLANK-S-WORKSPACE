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
Use Case ID	Use Case Name	Actor
UC001	View Live Bus Location	Student
UC002	Update Bus GPS Location	Driver
UC003	View Estimated Arrival Time (ETA)	Student
Subsystem 2: Route Recommender (Pin-to-Pin)
Use Case ID	Use Case Name	Actor
UC004	Plan Pin-to-Pin Route	Student
UC005	View Recommended Bus Route	Student
UC006	Manage Bus Stop Information	Admin
UC007	View Bus Stop Details	Student
Subsystem 3: Push Notifications for Delays & Cancellations
Use Case ID	Use Case Name	Actor
UC008	Subscribe to Bus Route Notifications	Student
UC009	Receive Delay or Cancellation Notification	Student / Admin
UC009B	View Notification Inbox	Student
Subsystem 4: Live Bus Occupancy Indicator
Use Case ID	Use Case Name	Actor
UC010	View Live Bus Occupancy Status	Student
UC011	Update Bus Occupancy Status	Driver
UC012	View Predicted Bus Crowd Level	Student
Summary Table
Subsystem	Number of Use Cases	Use Case IDs
GPS Live Tracking	3	UC001, UC002, UC003
Route Recommender	4	UC004, UC005, UC006, UC007
Push Notifications	3	UC008, UC009, UC009B
Live Occupancy Indicator	3	UC010, UC011, UC012
Total	12	UC001 – UC012
Actor Participation Summary
Actor	Use Cases	Total
Student	UC001, UC003, UC004, UC005, UC007, UC008, UC009, UC009B, UC010, UC012	10
Driver	UC002, UC011	2
Admin	UC006, UC009	2
Detailed Use Case Descriptions
<details> <summary><b>UC001: View Live Bus Location</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, GPS tracking active, Internet available
Flow	Student opens Live Tracking → System retrieves GPS coordinates → Displays bus locations on map
Postconditions	Real-time bus location displayed, tracking activity logged
</details><details> <summary><b>UC002: Update Bus GPS Location</b> (Click to expand)</summary>
Element	Description
Actor	Bus Driver
Preconditions	Driver logged in, GPS device enabled, Internet available
Flow	GPS device detects location → System retrieves coordinates → Updates GPS database
Postconditions	Latest bus location updated, students see updated tracking
</details><details> <summary><b>UC003: View Estimated Arrival Time (ETA)</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, GPS tracking active, Bus location available
Flow	Student selects bus stop/route → System calculates ETA → Displays arrival time
Postconditions	ETA displayed, request activity logged
</details><details> <summary><b>UC004: Plan Pin-to-Pin Route</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, Internet available, GPS enabled
Flow	Student selects origin & destination → System retrieves stops & routes → Displays recommended route
Postconditions	Recommended route displayed, travel info provided
</details><details> <summary><b>UC005: View Recommended Bus Route</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, Route recommendation data available
Flow	Student selects recommended route → System displays route path, ETA, and walking distance
Postconditions	Route details displayed, viewing activity logged
</details><details> <summary><b>UC006: Manage Bus Stop Information</b> (Click to expand)</summary>
Element	Description
Actor	Admin
Preconditions	Admin logged in, Valid admin privileges
Flow	Admin selects stop to update → Edits details → System validates and stores updates
Postconditions	Stop information updated, activity logged
</details><details> <summary><b>UC007: View Bus Stop Details</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, Bus stop data available
Flow	Student selects bus stop → System displays name, routes, ETA
Postconditions	Stop details displayed
</details><details> <summary><b>UC008: Subscribe to Bus Route Notifications</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, Internet available, Notification permissions enabled
Flow	Student opens Notification Settings → Selects routes/stops → System saves subscription
Postconditions	Subscription saved, student receives alerts
</details><details> <summary><b>UC009: Receive Delay or Cancellation Notification</b> (Click to expand)</summary>
Element	Description
Actor	Student, Admin
Preconditions	Student subscribed, Delay/cancellation event triggered
Flow	Admin/Driver triggers event → NotificationService queries subscribers → FCM sends push notifications
Postconditions	Subscribed students notified, notification saved to inbox
</details><details> <summary><b>UC009B: View Notification Inbox</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, At least one notification received
Flow	Student opens Notification Inbox → System fetches history → Displays chronological list
Postconditions	Notification history displayed correctly
</details><details> <summary><b>UC010: View Live Bus Occupancy Status</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, Occupancy monitoring active, Internet available
Flow	Student selects Bus Occupancy → System retrieves data → Displays color-coded status (Green/Yellow/Red)
Postconditions	Occupancy status displayed, viewing activity logged
</details><details> <summary><b>UC011: Update Bus Occupancy Status</b> (Click to expand)</summary>
Element	Description
Actor	Bus Driver
Preconditions	Driver logged in, Occupancy monitoring active, Internet available
Flow	Driver selects occupancy level (Empty/Moderate/Full) → System updates database
Postconditions	Occupancy status updated, students see latest data
</details><details> <summary><b>UC012: View Predicted Bus Crowd Level</b> (Click to expand)</summary>
Element	Description
Actor	Student
Preconditions	Student logged in, AI prediction service active, Historical data available
Flow	Student selects route/stop → System analyzes trends → Displays predicted crowd level
Postconditions	Prediction displayed, request activity logged
</details>
Use Case Coverage in Prototype
Use Case	Implemented In	Status
UC001	Student Live Map page	✅
UC002	Driver Dashboard → Update GPS	✅
UC003	Student Live Map (ETA countdown)	✅
UC004	Student Route Planner → Find Best Route	✅
UC005	Recommended Route page	✅
UC006	Admin Dashboard → Manage Stops	✅
UC007	Stop Details page	✅
UC008	Student Alerts → Subscription toggles	✅
UC009	Driver → Send Alert → Student Inbox updates	✅
UC009B	Student Alerts → Notification Inbox	✅
UC010	Student Occupancy page	✅
UC011	Driver Dashboard → Update Occupancy	✅
UC012	Student Occupancy → AI Insight card	✅
