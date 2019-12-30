TWITTER IMPLEMENTATION - COP5615: Fall 2019

TEAM INFO
--------------------------------------------------------------------------------------------------------
Chandan Chowdary Kandipati (UFID 6972-9002)
Gayathri Manogna Isireddy (UFID 9124-0699)

PROBLEM STATEMENT
--------------------------------------------------------------------------------------------------------
The goal of this project is to implement a Twitter Clone and a simulator in Elixir.

INSTALLATION AND RUN
---------------------------------------------------------------------------------------------------------
Elixir Mix project needs to be installed. The project lib folder contains the following files.

proj4.ex -> Main entry for the project, takes arguments from the command line.

client.ex -> Contains code for actor nodes and also the simulator in a different module

server.ex -> Contains server code which handles the requests coming from the clients

To run the project, do:

->Unzip contents to your desired elixir project folder.
->The executable file is already created under the name of proj4ex.
->To execute the file use the following command "./proj4ex <<number.of.clients>> <<number.of.tweets>>
->Optional => [If we want to compile the project and generate the executable file the following command needs to be executed in the path of project folder "mix escript.build".]

Upon running the project using above command, we will see the simulator getting started with the server starting in the first go and client nodes gets initialized next.
The clients gets registered to the server and the automation process starts.

To run the test cases, do:
mix test
Example:

chandan@chandan-HP-ENVY-x360-Convertible:~/Documents/proj4$ ./proj4ex 10 2

user1 registered
user2 registered
.
.
.
.
user4 went offline
-------- user1 requested for own tweets ---------

Live tweet ----> user5 tweeted: Hope everyone is doing good @user4
user2 went offline
Live tweet ----> user1 tweeted: #COP5615isgreat it is a good subject
user4 came online
-------- user3 requested for tweets with hashtag #HappyBirthday ---------

Live tweet ----> user4 tweeted: #HappyBirthday to you @user2
-------- user3 requested for own tweets ---------
#COP5615isgreat it is a good subject @user3
user3 went offline
user2 came online
Live tweet ----> user2 tweeted: #COP5615isgreat it is a good subject @user5
"All users tweeted"
Average time taken to register user: 32.6 us
Average time taken by the user to tweet: 60.666666666666664 us
Average time taken to get tweets with a specific hashtag: 74.0 us
Average time taken to get mentioned tweets: 61.0 us
Average time taken to get tweets of user: 58.0 us
Average time taken to subscribe to an user: 3029.3333333333335 us
Average time taken to get subscribers of user: 73.6 us
Average time taken to get the users that an user has subscribed to: 75.6 us


WHAT IS WORKING
--------------------------------------------------------------------------------------------------------------
A number of users are created and then simulation will start. Simulation is similar to twitter engine in which a number of users tweet, few subscribe to a user, retrieve the subscribers of a user, retrieving the users to whom a user is subscribed to, retrieve all the tweets of a user, retrieve the tweets tagged with hashtags, retrieve the tweets tagged with mentions, randomly few users go offline, few come online, retweeting the same tweets that are tweeted by a user and finally deleting the account of a user.

All of the followng functionalities hace been implemented:
1. Register account and delete account
2. Send tweet. Tweets can have hashtags (e.g. #COP5615isgreat) and mentions(@bestuser). You can use predefines categories of messages for hashtags.
3. Subscribe to user's tweets.
4. Re-tweets (so that your subscribers get an interesting tweet you got by other
means).
5. Allow querying tweets subscribed to, tweets with specific hashtags, tweets in which the user is mentioned (my mentions).
6. If the user is connected, deliver the above types of tweets live (without querying).
7. Several test cases have been written to check the project's output.

Below are the details of the test cases that we have created.
--------------------------------------------------------------
Test Case1- Registering a new user, “user1”.
Test Case2- Registering a new user, “user2”.
Test Case3- Registering a new user, “user3”.
Test Case 4- Checking whether the given user (user1) is already registered.
Test Case 5- Checking if the user tweet reaches the server
Test Case 6- Retrieving tweets that are tagged with HashTag(#).
Test Case 7- Checking whether a empty list is returning if the tweets with hashtag are not found.
Test Case 8 - Retrieving tweets that are tagged with Mentions(@).
Test Case 9- Checking whether a empty list is returning if the tweets with mention are not found.
Test Case 10- Retrieving the tweets tweeted by a particular user.
Test Case 11- Checking whether empty list is returning if a particular user has not tweeted yet.
Test Case 12- Subscribing one user to another user
Test Case 13- Retrieving all the subscribers of a particular user (“user2”)
Test Case 14- Checking whether a empty list is returning if there are no subscribers for a user (“user1”).
Test Case 15- Retrieving a list of users to whom a particular user (“user1”) is subscribed to.
Test Case 16- Checking whether a empty list is returning if a particular user (“user2”) is not subscribed to any users.
Test Case 17- Making a user (“user1”) go offline
Test Case 18- Making a user go online
Test Case 19- Checking if the user(“user2”) tweet reaches the server
Test Case 20- User (“user1”) retweeting the same tweet tweeted by another user (“user2”)
Test Case21- Deleting a user (“user1”)


Largest number of users that can be given to the project is 100000 with varied number of tweets. The project keeps on running until all the users tweeted and also the users perform according to the simulator.
