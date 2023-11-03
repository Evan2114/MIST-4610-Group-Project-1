# Team 8 MIST-4610-Group-Project-1

## Team Name
39217 Group 8

## Team Members
1. Ryan Alford
2. Khushi Patel
3. Evan Andersen [@Evan2114](https://github.com/Evan2114)
4. Elizabeth Carlin
5. Ethan Bowen
6. Purvi Nandakumar

## Problem Description
The relevant situation is that our client, the owner and chairman of Srini's Country Club, Dr. Nikhil Srinivasan, needed a relational database to track important data for his growing business. The central entity in the model is the Members entity because the members drive the revenue and activities of the entire business. The Members entity is directly tied to the Equipment, Guests, Memberships, and Instructors entities and associatively related to TeeTimes, Tournaments, and Events. We are interested in modeling these essential relationships, generating dummy data, and infusing the entities and their attributes with the corresponding data points. Most importantly, we intend to create multiple queries that provide crucial insights into Srini's Country Club, particularly data points linked to the Members, with the goal of identifying which areas of the business to optimize in the future.

## Client Conversations and Data Model

Explanation of client conversations:

As depicted via the screenshots, Dr. Srinivsan provided us with 18 components and services involved in his businesses, and described them in immense detail. These components are the entities in the relational data model below. Additionally, Dr. Srinivsan went into further detail about the attributes and primary keys within each entity, as well as the relationships between multiple entities. These conversations were essential in our creation of the complex data model. Moving forward, we decided to omit two of the components ("Inventory" and "Restaurants") because they were less relevant to the primary Members entity and were not utilized in our queries. 

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%201.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%202.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%203.png)

Explanation of data model:

Our model is based on the structure of Dr. Srinivasan's "Srini's Country Club". The primary entity is the Members entity. This entity contains all the necessary identifying data points of members, including a member specific memberID as the primary key, different contact information, member join date, and foreign keys from other tables that establish links to the Instructors and Memberships tables. Also, Members have a many-to-many relationship with TeeTimes because members can book multiple tee times, and each tee time can consist of multiple members. Thus, Members and TeeTimes create an associative entity, both having identifying relationships with the MemberBookings table since both primary keys comprise the composite primary key.

The Guests entity indicates the guests that members can bring alongside them, containing similar attributes to the Members entity. Members have a one-to-many relationships with Guests because members can bring along many guests, and it is a non-identifying relationship because guests do not have to be associated with just one member. Guests also have a many-to-many relationship with the TeeTimes table

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Data%20Model.png)

## Data Dictionary

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Courses.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Employees.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Equipment.png))

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Events.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/GolfCarts.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/GuestBookings.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Guests.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Instructors.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/MemberBookings.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/MemberEvents.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Members.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Memberships.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Member%20Tournaments.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/ProShop.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/TeeTimes.png)

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Tournaments.png)

## Queries

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Feature%20List.png)

1. Query 1 lists what tournaments that do not have any employees assigned to work.

2. Query 2 lists all the equipment in used condition and the price needed to replace them.

3. Query 3 displays the ID and quantity in stock of items in the pro shop ordered by highest to lowest sales.

4. Query 4 lists all members and their total expenses, which includes membership fees and equipment rentals. The results are grouped by member and sorted in descending order of total expenses.

5. Query 5 retrieves the names of all members who have booked tee times in the last 30 days, and displays the number of tee times they have booked.

6. Query 6 lists the instructor names and their certification level only for those instructors whose members have played in 1 or less tournament.

7. Query 7 calculates the occupancy rate for the entire country club by considering all tee times.

8. Query 8 determines the top 3 members who have hosted the most events at the country club.

9. Query 9 retrieves the names of all members who have booked at least one tee time but have not hosted any events.

10. Query 10 retrieves the IDs and par ratings of all courses. The results are ordered from least to most difficult.

## Database Information
Name of the database: ns_F2339217Group8

Additional information: Each query listed above is indicated in the database using stored procedures which can be called using the following format: CALL TP_Qx();
