# Film Hub - Josh Narvaez

We use redux toolkit which is a state management tool. We wrap our app in Provider which allows redux toolkit to manage the state of our entire app.
https://redux-toolkit.js.org/

we use the movie database tmdb api to get our data
https://www.themoviedb.org/?language=en-US


Authentication starts at Navbar. First, we click the login button which goes to the fetchToken function in /utils. fetchToken is an asynchronous function that makes a GET request to '/authentication/token/new' ---- creates the authentication token. If it is successful, set it to localStorage and then redirect to the authentication page.

Then user will be authenticated, they will approve, and then we will redirect back to the navigation bar. There, we look for updates to the user token. If the token is updated, we call the login function. If there is a token we make a post request to create a new authentication session. Then, we store it to localStorage.

Once we do that, we get a sessionId. Then, we can get the userData and dispaatch the function to set the user to be in our entire application state. Once, we set this user to the state, we can then use this user whenever we want.

We use Alan AI voice assistant to execute some simple voice commands. We connect our app with Alan using an API key. We write scripts on Alan's app and pass in an array of genres to build out our voice assistant.