# Home repo for a school assignment

# Child repos
* front end: [fe-hacker-news](https://github.com/HackerNews-lsd2017/fe-hacker-news)
* back end: [be-hacker-news](https://github.com/HackerNews-lsd2017/be-hacker-news)

# Assignment #6 - KNA Toolbox
## Large System Development

## Logical Data Model
![alt text](https://github.com/HackerNews-lsd2017/hacker-news/blob/master/screenshots/Screen%20Shot%202017-10-24%20at%2017.46.37.png)

## Use Case Model
![alt text](https://github.com/HackerNews-lsd2017/hacker-news/blob/master/screenshots/Screen%20Shot%202017-10-24%20at%2023.11.21.png)

#### Use Case: Log in
CHARACTERISTIC INFORMATION
Goal in Context: Registered User makes an authentication request and expects to log, in order to use full functionality of the system 

Scope: System under design

Level: Underwater

Preconditions: User has an account.

Success End Condition: User is authenticated.

Failed End Condition: User has an account and he can’t log in. 

Primary Actor: Registered user

Trigger: authentication request comes in

MAIN SUCCESS SCENARIO

1. User makes an authentication request.
2. Server captures authentication request.
3. Server is looking up user credentials in database.
4. Server authenticates user
5. Server returns a response that user has been authenticated
6. User logs in and he is able to use functionality of an registered user

Brief description:

Users puts his username and password and expects to get logged in.

#### Use Case: Register
CHARACTERISTIC INFORMATION

Goal in Context: User makes an account creation request and expects to that account is created

Scope: System under design

Level: Sea

Preconditions: Guest has to specify username, password and email address.

Success End Condition: Account is created.

Failed End Condition: Account is not created

Primary Actor: Guest

Trigger: Request for new account comes in

MAIN SUCCESS SCENARIO

1. Guest provides all necessary data to create an account.
2. Guest is pressing the button which sends request to server.
3. Server is persisting user data in database.
4. Server sends confirmation mail.
5. Guest authenticates himself using the link received in mail.
6. Guest receives information that now he is an user.

Brief description:

Guest provides information necessary to create an account and expects that application is going to create his account.

#### Use Case: View post

CHARACTERISTIC INFORMATION

Goal in Context: User or guest is able to view content of post.

Scope: System under design

Level: Sea

Preconditions: None

Success End Condition: User views the content of post.

Failed End Condition: User is not able to see the content of post.

Primary Actor: Guest/User

Trigger: 
- User clicks the thread and sees posts connected with it.
- User presses search with parameters that match some kind of post.

MAIN SUCCESS SCENARIO

1. Guest/User is making a request for post content.
2. Content of post is being extracted from database.
3. Post is being sent as a response to guest/user.
4. Post is being presented to guest/user.
5. Guest/user is viewing the content of post.

Brief description:

User/Guest makes a request to see a post and it is presented to him.

#### Use Case: Find post

CHARACTERISTIC INFORMATION

Goal in Context: User or guest using certain search criteria expects to find relevant post.

Scope: System under design

Level: Underwater

Preconditions: None

Success End Condition: User finds relevant post.

Failed End Condition: User does not find relevant post.

Primary Actor: Guest/User

Trigger: 
 
User presses search with parameters that match some kind of post.

MAIN SUCCESS SCENARIO

1. Guest/User is making a request for post content.
2. Content of post is being extracted from database.
3. Post is being sent as a response to guest/user.
4. Post is being presented to guest/user.
5. Guest/user is viewing the content of post.

Brief description:

User/Guest makes a request to see a post and it is presented to him.

#### Use Case: Comment post

CHARACTERISTIC INFORMATION

Goal in Context: User wants to respond to post and expects that his comment will be attached to post.

Scope: System under design

Level: Sea

Preconditions: User found the post. User is logged in.

Success End Condition: User commented post that he wanted.

Failed End Condition: User did not succeed to comment post that he wanted.

Primary Actor: User

Trigger: User presses button comment and request is being sent to server to persist the message and append it to relevant post.

MAIN SUCCESS SCENARIO

1. Guest/User is creating content of comment
2. Server receives request to persist the comment and append it to relevant post.
3. Server persists comment in the database with connection to relevant post.
4. User receives response from server that comment has been persisted and added to relevant post.
5. User can see his comment to relevant post.

Brief description:

User/Guest makes a comment that is being persisted and presented to him and other users.

Extension: Report post

User reports post that in his/her belief is violating some rules of the website.

#### Use Case: Update user

CHARACTERISTIC INFORMATION

Goal in Context: User is changing his information and expects that applications updates is accordingly to changes that he/she provided.

Scope: System under design

Level: Sea

Preconditions: User has an account.

Success End Condition: User information is updated

Failed End Condition: User information is not updated.

Primary Actor: Registered user

Trigger: Update request comes in.

MAIN SUCCESS SCENARIO

1. User is editing his information.
2. User clicks the button that sends request to server to persist his/her changes.
3. Server overrides previous information about user with changes that were requested by user.
4. Server sends response that operation has been successful
5. Information about persisted changes are being presented to user.

Brief description:

User sends updated information about his/her account which is persisted in database.

#### Use Case: Create Post

CHARACTERISTIC INFORMATION

Goal in Context: User provides content of post and expects that it is going to be posted on website.

Scope: System under design

Level: Sea

Preconditions: User has an account.

Success End Condition: Post is created and persisted.

Failed End Condition: Post is not created or it is not persisted.

Primary Actor: Registered user

Trigger: User is pressing “Create Post” button and post request comes to server.

MAIN SUCCESS SCENARIO

1. User creates content of post
2. User is click a button that sends post request to server.
3. Server is persisting post in a database.
4. Server makes publishes post so others can view it.
5. Server returns a response to user that post has been successfully created.
6. Information about successful post is being presented to user.

Brief description:

User creates post that is being published and persisted.

#### Use Case: Log out

CHARACTERISTIC INFORMATION

Goal in Context: Logged in user makes a request to logout and expects to lose access to the system. 

Scope:  System under design

Level: Underwater

Preconditions: User is logged in

Success End Condition: User is logged out

Failed End Condition: User is not logged out

Primary Actor: Registered user

Trigger: Logout button is being pressed

MAIN SUCCESS SCENARIO

1. User is pressing a logout button.
2. User session is being deleted.
3. Information is being presented to a user acknowledging that he he/she been logged out.

Brief description:

User is pressing logout button and his session is being deleted.

#### Use Case: Vote Post

CHARACTERISTIC INFORMATION

Goal in Context: User votes up or down post and expects that his reaction is going to be recorded and included in total karma count.

Scope:  System under design

Level: Underwater

Preconditions: User has an account. In case of downvote user has to have enough karma

Success End Condition: Vote count has changed. One point up or down.

Failed End Condition:Vote count has not changed or it changed more than 1 point up or down.

Primary Actor: Registered user or registered user with high enough karma in case of downvote.

Trigger: User presses vote or downvote button.

MAIN SUCCESS SCENARIO

1. User clicks the vote button.
2. Server captures vote/downvote request.
3. Server is changing karma score of post that has been upvoted/downvoted.
4. Server is changing karma score of user that is a owner of post/comment that is a subject of this operation.
5. Server returns a response to a user that his action has been recorded and took effect.
6. Response is being presented to user that was responsible for upvote/downvote

Brief description:

Users upvotes/downvotes comment or post and his action is included in karma deduction.
 
Description of actors and responsabilities.
