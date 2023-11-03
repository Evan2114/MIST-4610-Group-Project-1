# Team 8 MIST-4610-Group-Project-1

## Team Name
39217 Group 8

## Team Members
1. Ryan Alford
2. Khushi Patel
3. Elizabeth Carlin
4. Ethan Bowen
5. Purvi Nandakumar

## Problem Description
The relevant situation is that our client, the owner and chairman of Srini's Country Club, Dr. Nikhil Srinivasan, needed a relational database to track important data for his growing business. The central entity in the model is the Members entity because the members drive the revenue and activities of the entire business. The Members entity is directly tied to the Equipment, Guests, Memberships, and Instructors entities and associatively related to TeeTimes, Tournaments, and Events. We are interested in modeling these essential relationships, generating dummy data, and infusing the entities and their attributes with the corresponding data points. Most importantly, we intend to create multiple queries that provide crucial insights into Srini's Country Club, particularly data points linked to the Members, with the goal of identifying which areas of the business to optimize in the future.

## Client Conversations and Data Model

Explanation of client conversations:

As depicted via the screenshots, Dr. Srinivsan provided us with 18 components and services involved in his businesses, and described them in immense detail. These components are the entities in the relational data model below. Additionally, Dr. Srinivsan went into further detail about the attributes and primary keys within each entity, as well as the relationships between multiple entities. These conversations were essential in our creation of the complex data model.

![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%201.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%202.png)
![Alt Text](https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Conversation%203.png)

Explanation of data model: An explanation of the data model including the relationships between the entities in natural English. 

Our model is based on the structure of Dr. Srinivasan's "Srini's Country Club". The primary entity is the Members entity. This entity contains all the necessary identifying data points of members, including a member specific memberID as the primary key, different contact information, member join date, and foreign keys from other tables that establish links to the Instructors and Memberships tables. Also, Members have a many-to-many relationship with TeeTimes because members can book multiple tee times, and each tee time can consist of multiple members. Thus, Members and TeeTimes create an associative entity, both having identifying relationships with the MemberBookings table since both primary keys comprise the composite primary key.

The Guests entity indicates the guests that members can bring alongside them, containing similar attributes to the Members entity. Members have a one-to-many relationships with Guests because members can bring along many guests, and it is a non-identifying relationship because guests do not have to be associated with just one member. Guests also have a many-to-many relationship with the TeeTimes table

![Alt Text] (https://github.com/Evan2114/MIST-4610-Group-Project-1/blob/main/Data%20Model.png)


## Database Information
Name of the database: ns_F2339217Group8

Additional information: Each query listed above is indicated in the database using stored procedures which can be called using the following format: CALL TP_Qx();
