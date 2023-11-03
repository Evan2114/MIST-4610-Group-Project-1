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

Query 1 is useful in determining the need for staffing. As part of the tournament planning process our golf club might need to assess coverage, and the first place a manager would look to fill gaps is tournaments that lack any staffing.

2. Query 2 lists all the equipment in used condition and the price needed to replace them.

Query 2 is also extremely practical, and might be completed as part of an inventory between busy seasons. Managers at a golf club want to replace the equipment in the worst condition first, so sorting by that is the most useful. Having the replacement cost immediately available is also good because it's relevant to replacement decisions. 

3. Query 3 displays the ID and quantity in stock of items in the pro shop ordered by highest to lowest sales.

Query 3 would be useful to determine which products we might keep in the store and which ones we might discontinue. Pulling the ID ensures we catch every product incase they have similar/ the same names. 

4. Query 4 lists all members and their total expenses, which includes membership fees and equipment rentals. The results are grouped by member and sorted in descending order of total expenses.

Query 4 is useful in a customer service setting. In the case of members canceling their membership or having billing errors, active records of a member’s expenses are extremely useful. This info is also useful in determining customer loyalty or for studying what types of customers spend the most. 

5. Query 5 retrieves the names of all members who have booked tee times in the last 30 days, and displays the number of tee times they have booked.

Query 5 is useful in creating projections for what the next month might look like. Club regulars will obviously appear more often, and we can cater to their habits if we know who they are. 

6. Query 6 lists the instructor names and their certification level only for those instructors whose members have played in 1 or less tournament.

Query 6 may be a phenomenal performance evaluation tool. If an instructor isn’t sending a lot of players to tournaments it might have something to do with their performance. Granted, there could be other causes but it's still good to cast an appropriately wide net with this query. 

7. Query 7 calculates the occupancy rate for the entire country club by considering all tee times.

Query 7 is great for monitoring which tees are open at a given time, and can help with booking. It's also good for figuring out our revenue before the invoices have been sent for the reservations. 

8. Query 8 determines the top 3 members who have hosted the most events at the country club.

Query 8 helps us really isolate our top hosting members from the rest. This would be good in a setting where there is either a prize or some other reward for top members, and the best way to figure that out would be this query. Its similar to when UGA’s top donors are recognized at football games. They need to know how to find who gives the most money. 

9. Query 9 retrieves the names of all members who have booked at least one tee time but have not hosted any events.

Query 9  helps us determine who our less active members are. Their low activity level might be an indicator that they aren’t satisfied, and so singling out these members is a great way to figure out who we should be gathering feedback from.

10. Query 10 retrieves the IDs and par ratings of all courses. The results are ordered from least to most difficult.

Query 10 is important because in a situation where one of our employees is asked about course difficulty, the best way to ensure that they have an accurate picture is to have a par rating query ready to go. This way if the manager doesn't have the knowledge on hand, they can look it up with this as well. 

## Database Information
Name of the database: ns_F2339217Group8

Additional information: Each query listed above is indicated in the database using stored procedures which can be called using the following format: CALL TP_Qx();
