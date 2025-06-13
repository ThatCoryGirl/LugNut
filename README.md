LugNut -- The Car Maintenance Mileage Interval App

Technologies used: Figma.com for brainstorming app, SQLite3, SQLite, GitHub Desktop,

Introduction and a Problem Worth Solving:

I cofounded a carclub in my area. I have found that there are many apps for Fleet Vehicle Maintenance but not for personal maintenance. Even as a car enthusiast it is hard to keep track of where I got my tires from and what the mileage warranty is or when my last oil change was or how many miles I have left before it needs to be changed. Or maybe I change my oil myself and want to find out where the best deals are for oil filters. I want this app to be an all encompassing place to keep track of all of my car needs. I used to rely heavily on forums but now there are 50 billion different social media platforms and groups to follow instead. It can be nervewracking.

Methodology:

Datasets gathered from ChatGPT and personal car knowledge. As this is just a demo, the dataset was created by me. I own a 2017 Subaru Impreza WRX Limited so the focus will be on this type of performance vehicle. Mileage maintenance is considered "proprietary" therefore I did not webscrape or purchase any datasets at this time. I hosted my dataset on a SQLite server for now.

Objective:

I want to be able to have the app plug in my vehicle details, create a profile, then notify me when it needs maintenance. That is to be its primary function but I do believe the app could have the potential for other things like a car friends social side, a local repair/maintenance shop review corner, performance part information, and finally warranty info on things I've purchased and from where.

Structure:

I have three Tables in my database:

  maintenance_schedule for maintenance service intervals
  
  user_vehicle for tracking each user's car plus their current car mileage and projected use
  
  user_service_logs for real-world service history plus optional photos and categories

Some additional nuggets:

  vehicle_nickname for personalization

  service_type for further classification

  photo_path for receipt/work order snaps
  

Use Cases:

You're trying to estimate the current mileage of a vehicle in the database:

mileage_est = mileage_last_known + months_since_update * est_miles_per_month

If you're trying to find the next scheduled service for a specific make and model based on mileage:

SELECT * FROM maintenance_schedule

WHERE make = 'Subaru' AND model = 'ImprezaWRX'

AND mileage >= mileage_est

ORDER BY mileage ASC

LIMIT 1;

Ideas for this Application:

  Notifications - query services due in or around 1000 miles

  Timeline - A visualization of service history per vehicle

  Image Upload - For quicker uploads and data collection and file storage

  Predictive Mileage - use case mileage_last_know + est_miles_per_month * months_elapsed

  Test Queries - Compare user_service_logs to maintenance_schedule

  Add User Interface - Hook this into a front end like Flutter, React Native, Swift or other
  

Conclusions:

Critiques & Suggestions from Mentors:

Citations:

Application Created By Cory Chapman
