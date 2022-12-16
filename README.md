# Project: Film Hub
## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Built With](#built-with)
- [Dependencies](#dependencies)
- [What We Learned](#what-we-learned)
- [Acknowledgements](#acknowledgements)

## Overview
![Alt text](/assets/images/screenshot.png?raw=true "Film Hub Screenshot")

 Live demo: https://jn-film-hub.netlify.app/ 
 
## Features
This application enables users to browse movies and related information such as ratings, trailers, cast members, etc. We accomplish this by fetching data from The Movie Database(TMDB) API. In addition to browsing movie details, users can save their favorite movies and add movies to a watchlist which can be accessed by clicking "My Movies" in the top right corner. We accomplish this by autenticating users which begins at the Navbar. First, we click the login button which calls the fetchToken function in /utils. fetchToken is an asynchronous function that makes a GET request to '/authentication/token/new' and creates the authentication token. If it is successful,  we set it to localStorage and then redirect to the authentication page.

Then, users will be authenticated, they will approve, and we will redirect back to the navigation bar. There, we look for updates to the user token. If the token is updated, we call the login function. If there is a token, we make a post request to create a new authentication session. Then, we store it to localStorage. Once we do that, we get a sessionId. Then, we can get the userData and dispatch the function to set the user to be in our entire application state. 

We manage the state of our entire application using Redux Toolkit. We accomplish this by wrapping our app in the Provider component and adding the store variable so it is accessible in every component of our application. We then create a file in our app folder called store.js which holds the configuration 
for our redux store and import the file to index.js so it can be used.

We also implement dark mode in our application. Users can activate dark mode by toggling the switch in the Navbar or clicking the microphone button in the bottom right corner and saying "dark mode". We accomplish this by integrating our app with Alan AI using an API key. When a user clicks the microphone button, they are interacting with Alan AI voice assisstant. We configured Alan AI to execute some other simple voice commands as well. Users can change categories of movies simply by saying whatever category they would like to see.  We then write scripts on Alan's app and pass in an array of genres to build out our voice assistant.

## Built With
The Movie Database API: https://www.themoviedb.org/?language=en-US  
React JS: https://reactjs.org/  
Node JS: https://nodejs.org/en/  
Redux Toolkit: https://redux-toolkit.js.org/   
MaterialUI: https://mui.com/
Alan AI: https://alan.app/docs/  
Axios: https://axios-http.com/docs/intro  
Netlify: https://www.netlify.com/

## Dependencies
npm install @alan-ai/alan-sdk-web @emotion/react @emotion/styled @mui/icons-material @mui/material @mui/styles @reduxjs/toolkit @testing-library/jest-dom @testing-library/react @testing-library/user-event axios react react-dom react-redux react-router-dom react-scripts web-vitals

## What We Learned
How to authenticate users, managing the state of our entire application using Redux Toolkit, implementing dark mode functionality, and Alan AI voice assistant
 
## Acknowledgements
Adrian Hajdin - JavascriptMastery JSM 