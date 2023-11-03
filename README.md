# Team 8 MIST 4610 Group Project 1

## Team Name
39217 Group 8

## Team Members
1. Ryan Alford [@Axeophone](https://github.com/Axeophone)
2. Khushi Patel 
3. Evan Andersen [@Evan2114](https://github.com/Evan2114)
4. Elizabeth Carlin [@elizabethcarlin](https://github.com/elizabethcarlin)
5. Ethan Bowen [@EthanB57](https://github.com/EthanB57)
6. Purvi Nandakumar [DISCLAIMER] - Our team member is currently out of the country and does not have access to any communcication with us, so we do not currently have her GitHub link. However, she was involved in the project in the earlier stages and did contribute in anticipation of her trip.

## Problem Description
The relevant situation is that our client, the owner and chairman of Srini's Country Club, Dr. Nikhil Srinivasan, needed a relational database to track important data for his growing business. The central entity in the model is the Members entity because the members drive the revenue and activities of the entire business. The Members entity is directly tied to the Equipment, Guests, Memberships, and Instructors entities and associatively related to TeeTimes, Tournaments, and Events. We are interested in modeling these essential relationships, generating dummy data, and infusing the entities and their attributes with the corresponding data points. Most importantly, we intend to create multiple queries that provide crucial insights into Srini's Country Club, particularly data points linked to the Members, with the goal of identifying which areas of the business to optimize in the future.

## Client Conversations and Data Model

Explanation of client conversations:

As depicted via the screenshots, Dr. Srinivsan provided us with 18 components and services involved in his businesses, and described them in immense detail. These components are the entities in the relational data model below. Additionally, Dr. Srinivsan went into further detail about the attributes and primary keys within each entity, as well as the relationships between multiple entities. These conversations were essential in our creation of the complex data model. Moving forward, we decided to omit two of the components ("Inventory" and "Restaurants") because they were less relevant to the primary Members entity and were not utilized in our queries. 

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%201.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%202.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%203.png)

Explanation of data model:

In the process of creating our database, we made a few changes to Attribute and Entity Names as well as Data Types. Initially, we created our Primary Keys to be of the VARCHAR(6) data Type but for functionality purposes we increased the character count to 25 across the board. Generic Attribute names like “Name”, “Date”, “Contact information”, “Description”, and others that were given to us by the client are not useful and so in most cases, we appended the table name to the front of the attribute name. In some cases, we also split up a request attribute into two attributes, as storing multiple pieces of data in the same column breaks normal form conventions. Our client did seem to think that names and contact information could be stored in single entities, however with brief edits, the database became much more functional, readable, and intuitive. To give an example “name” was a desired attribute for the “Guest” entity but was also requested in several other entities, so we created guestFName and guestLname for the guest table, and distinctly labeled *TableName*_Name attributes for the other entities. We also decided to rename some entities from what the client requested. Namely, the word Golf was removed from many of the attributes both to save space and to increase readability (users won't have to look at which “Golf” Entity they are looking at if they don’t start with that word).
-Golf Tournaments was changed to “Tournaments”
-Pro Shop Items was changed to “ProShop”
-Golf Instructors was changed to “Instructors”
-Rental Equipment was changed to “Equipment”

Our model is based on the structure of Dr. Srinivasan's "Srini's Country Club". The primary entity is the Members entity. This entity contains all the necessary identifying data points of members, including a member specific memberID as the primary key, different contact information, member join date, and foreign keys from other tables that establish links to the Instructors and Memberships tables. Also, Members have a many-to-many relationship with TeeTimes because members can book multiple tee times, and each tee time can consist of multiple members. Thus, Members and TeeTimes create an associative entity, both having identifying relationships with the MemberBookings table since both primary keys comprise the composite primary key.

The Guests entity indicates the guests that members can bring alongside them, containing similar attributes to the Members entity. Members have a one-to-many relationships with Guests because members can bring along many guests, and it is a non-identifying relationship because guests do not have to be associated with just one member. Guests also have a many-to-many relationship with the TeeTimes table because guests can go to multiple TeeTimes and TeeTimes can contain a multitude of guests.

TeeTimes are, of course, associated with our golf courses which we store information about difficulty, length, and a brief description of each course. We wouldn’t want our members to not know what they are signing up for.Tee Times are also associated with our Golf carts which are optionally allowed to be assigned to each booking. Not all Caddies wish to have a cart, but many do and therefore it’s important that we track the status of each cart both with regard to its rental status and its condition. 

Alongside Members and Guests, another crucial pillar of our golf club is the equipment we have on hand for use by club members. This includes everything you might need to play the game and as such we’ve given each piece of equipment and ID, a name, a rental price, and a quantity we have in stock at a given time. We also track the equipment’s condition at a given time as the last thing we’d want to do is give our members shoddy equipment. 

Equipment available for rental is often also for sale in the ProShop albeit at a different price. For ProShop items that are also equipment, we have a one-to-many relationship documented such that we don’t store redundant data. 

Our members also receive top-notch instruction from our club’s on-staff instructors. As such we track identifying information about our instructors as well as their certification level and specialties. These instructors, though they work in one-on-one sessions, can be assigned to more than one member at a time and therefore we’ve modeled that relationship.

Members may also participate in two other categories of events that we track data for Tournaments and Events. Tournaments are the lifeblood of a proper golf club, and we track extensively the name, date, entry fees, and type of each of these competitive events. Our non-tournament events, like parties, cooperate retreats, or other such events are similarly tracked but a separate distinction was given to them as they have much wider variation than tournaments. Still, though we track many of the same attributes as tournaments with the distinction that most of these events don’t have an entry fee. 

And of course, we wouldn’t be a proper country club without the staff to facilitate our events and tournaments. Associated with both of the aforementioned entities in the same capacity, our employees are assigned on an event-to-event basis. Those not assigned to events are either off work or work a job that does not include facilitating such things. As such we store identifiable information, hire date, job title, and contact information for all of our employees. 

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Data%20Model.png)

## Data Dictionary

***GENERAL NOTE: We already populated our tables with data, so we were unable to change the internal database to match the data dictionary/data model. However, for each table with an ID code, the table in mySQL reflects VARCHAR(25) instead of VARCHAR(6) expressed in the data dictionaries/data model. The reasoning for this is that we wanted to add extra leeway for Dr. Srinivasan and his database in case the ID numbers needed to expand with the acquisition of new members.

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

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Feature%20Table.png)

1. Query 1 lists what tournaments that do not have any employees assigned to work.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%201.png)

Query 1 is useful in determining the need for staffing. As part of the tournament planning process our golf club might need to assess coverage, and the first place a manager would look to fill gaps is tournaments that lack any staffing.

2. Query 2 lists all the equipment in used condition and the price needed to replace them.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%202.png)

Query 2 is also extremely practical, and might be completed as part of an inventory between busy seasons. Managers at a golf club want to replace the equipment in the worst condition first, so sorting by that is the most useful. Having the replacement cost immediately available is also good because it's relevant to replacement decisions. 

3. Query 3 displays the ID and quantity in stock of items in the pro shop ordered by highest to lowest sales.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%203.png)

Query 3 would be useful to determine which products we might keep in the store and which ones we might discontinue. Pulling the ID ensures we catch every product incase they have similar/ the same names. 

4. Query 4 lists all members and their total expenses, which includes membership fees and equipment rentals. The results are grouped by member and sorted in descending order of total expenses.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%204.png)

Query 4 is useful in a customer service setting. In the case of members canceling their membership or having billing errors, active records of a member’s expenses are extremely useful. This info is also useful in determining customer loyalty or for studying what types of customers spend the most. 

5. Query 5 retrieves the names of all members who have booked tee times in the last 30 days, and displays the number of tee times they have booked.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%205.png)

Query 5 is useful in creating projections for what the next month might look like. Club regulars will obviously appear more often, and we can cater to their habits if we know who they are. 

6. Query 6 lists the instructor names and their certification level only for those instructors whose members have played in 1 or less tournament.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%206.png)

Query 6 may be a phenomenal performance evaluation tool. If an instructor isn’t sending a lot of players to tournaments it might have something to do with their performance. Granted, there could be other causes but it's still good to cast an appropriately wide net with this query. 

7. Query 7 calculates the occupancy rate for the entire country club by considering all tee times.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%207.png)

Query 7 is great for monitoring which tees are open at a given time, and can help with booking. It's also good for figuring out our revenue before the invoices have been sent for the reservations. 

8. Query 8 determines the top 3 members who have hosted the most events at the country club.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%208.png)

Query 8 helps us really isolate our top hosting members from the rest. This would be good in a setting where there is either a prize or some other reward for top members, and the best way to figure that out would be this query. Its similar to when UGA’s top donors are recognized at football games. They need to know how to find who gives the most money. 

9. Query 9 retrieves the names of all members who have booked at least one tee time but have not hosted any events.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%209.png)

Query 9  helps us determine who our less active members are. Their low activity level might be an indicator that they aren’t satisfied, and so singling out these members is a great way to figure out who we should be gathering feedback from.

10. Query 10 retrieves the IDs and par ratings of all courses. The results are ordered from least to most difficult.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Query%2010.png)

Query 10 is important because in a situation where one of our employees is asked about course difficulty, the best way to ensure that they have an accurate picture is to have a par rating query ready to go. This way if the manager doesn't have the knowledge on hand, they can look it up with this as well. 

## Database Information
Name of the database: ns_F2339217Group8

Additional information: Each query listed above is indicated in the database using stored procedures which can be called using the following format: "CALL TP_Qx();" The 'x' indicates which query you intend to seek the results from.
