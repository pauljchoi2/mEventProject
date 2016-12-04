# mEvent

### Link to the website
http://mevent.herokuapp.com/

### Description

#### Login Screen
When the user first loads the website, they are brought to a screen with 2 form fields - one of which being the Login form, and the other being the Sign Up form. The Sign Up form requires a Username, a Password, a First Name, and a Last Name, with appropriate form validation in place to ensure all inputs are valid. Once the Sign Up button at the bottom has been pressed, each of the attributes are saved in a PSQL table, with the Username being the Primary Key. Another attribute that is automatically created is the account type (whether they are admins or not). We have, by default, set all new accounts to be clients by default. All admins on the website are either preexisting or need to be added into the database manually. The Sign In form requires a Username and a Password. The form sends the input fields to the server, gets the user information from the database (using the Username as the Primary Key) and checks the passwords against each other. If the information matches up, a session is created. The session ensures that all user info persists throughout their usage of the website. Everytime a new page is loaded, the server checks to ensure that a session exists - this is a security mechanism to make sure that users can only access the pages that they are designed to access, as well as a way to ensure that user data persists throughout their usage of the website. There is also a navigation bar at the top containing a link to the login screen, which exists should a user need to refresh the login screen.

#### Main Page
##### Navigation Bar
Once the user has logged in, there are four main components that they will be able to interact with. The first component is the navigation bar at the top. There are three buttons on the navigation bar: the Home button, the Add Event button, the Admin button, and the Logout button. The Home button simply redirects the user to the Main Page, the Add Event button brings the user to a page where they can create Events, and the Admin button brings the user to a page containing all Administrator functionality. The Admin button only appears if the user's account type is Admin, otherwise it appears as an empty <div></div>. The check is performed with the use of the existing session, and occurs everytime the navigation bar is loaded. This is to ensure that only users with the appropriate permissions can use the Administrator functions. The logout button terminates the current session, and redirects the user to the login screen. The navigation bar appears on every page to ensure that users can access all of the website's features from any page.
