---
title: Travel Tracker  
length: 1 week
tags: javascript, oop, testing, jquery
---

## Background and Description

For this project, you will be creating an application to manage and track different trips for users and a travel agency.

## Goals and Objectives

- Use OOP to drive the design of the application and the code
- Work with an API to send and receive data
- Solidify the code review process
- Create a robust test suite that thoroughly tests all functionality of a client-side application

# Requirements

## Technologies

* **the fetch API** to retrieve and add data
* **Sass** for getting fancy with your CSS
* **Mocha** and **Chai** for testing your code

## Initial Setup

For this project, you will want to use this [Webpack Starter Kit](https://github.com/turingschool-examples/webpack-starter-kit){:target='blank'} repo. Setup instructions are in the README.  You will also need to clone down this [local server](https://github.com/turingschool-examples/travel-tracker-api){:target='blank'} and have it running in a separate tab in your terminal each time you run your client.

### Endpoints

Below are all the endpoints set up for this project. You may not use all of them -- some apply to extensions. Pay attention to the functionality required of each iteration when picking the appropriate endpoint.

| Description | URL | Method | Required Properties for Request | Sample Successful Response |
|----------|-----|--------|---------------------|-----------------|
| Get all travelers|`http://localhost:3001/api/v1/travelers`| GET  | none | object with `travelers` property containing an array of all travelers |
|Get single traveler|`http://localhost:3001/api/v1/travelers/<id>`     *where`<id>` will be a number of a traveler's id* | GET  | none | object of single traveler's info |
|Get all trips| `http://localhost:3001/api/v1/trips` | GET | none | object with `trips` property containing an array of all trips |
|Get all destinations| `http://localhost:3001/api/v1/destinations` | GET | none | object with `destinations` property containing an array of all destinations |
| Add new trip |`http://localhost:3001/api/v1/trips`| POST | `{id: <number>, userID: <number>, destinationID: <number>, travelers: <number>, date: <string 'YYYY/MM/DD'>, duration: <number>, status: <string 'approved' or 'pending'>, suggestedActivities: <array of strings>}` | `{message: 'Trip with id <id> successfully posted', newTrip: <Object with trip info just posted>}`|
| Add new destination|`http://localhost:3001/api/v1/destinations`| POST | `{id: <number>, destination: <string>, estimatedLodgingCostPerDay: <number>, estimatedFlightCostPerPerson: <number>, image: <string>, alt: <string>}` | `{message: 'Destination with id <id> successfully posted', newDestination: <Object with destination info just posted>}`|
| Modify single trip | `http://localhost:3001/api/v1/updateTrip` | POST | `{id: <number>, status:<String of 'approved' or 'pending', suggestedActivities: <Array of strings>}` *Only a status* **or** *a suggestedActivities property is required for a successful request*| `{message: 'Trip #<id> has been modified', updatedTrip: <Object with newly updated data>}`|
| Delete single trip| `http://localhost:3001/api/v1/trips/<id>`     *where`<id>` will be a number of a trip's id*  | DELETE | none | Trip #<id> has been deleted |

<section class="note">
### Note

* All POST and DELETE requests should have the following headers:
```js
{
  "Content-Type": "application/json"
}
```

* Remember, a `.catch` won't necessarily run on a bad response (ie 4xx level status) from the server. Make sure you're checking your response status codes and messages if something isn't working as expected
</section>

## Iterations

### 1. Dashboard

**As a traveler:**
- I should see a dashboard page that shows me:
    - All of my trips (past, present, upcoming and pending)
    - Total amount I have spent on trips this year. This should be calculated from the trips data and include a travel agent's 10% fee

### 2. Traveler Interaction

**As a traveler:**
- I should be able to make a trip request:
    - I will select a date, duration, number of travelers and choose from a list of destinations
    - After making these selections, I should see an estimated cost (with a 10% travel agent fee) for the trip.
    - Once I submit the trip request, it will show on my dashboard as "pending" so that the travel agency can approve or deny it. 

**Refer to the "Add new trip" section from the endpoints table above!** 

<section class="note">
### Note!

If you haven't already, focus on accessibility at this point.  Before moving to iteration 3, please **create a branch and push it up to GH** so instructors can run *Lighthouse* and check your dashboard for it's accessibility audit.
</section>

### 3. Login

When first arriving at the site, a user should be able to log in with a username and password.

**As a traveler:** 
- I should be able to login:
  - I will see a login page when I first visit the site:
  - I can log in with the following credentials:

```
username: traveler50 (where 50 is the ID of the user)
password: travel2020
```

  - Upon successfully loggin in, I should see my dashboard.

**Refer to the "Get single traveler" section from the endpoints table above!** 

### 4. Agent Interaction

Your app should now support two different types of users.  In addition to having a traveler, you will now add a travel agency. 


**As a travel agent:**
- I should be able to login:
  - I will see a login page when I first visit the site:
  - I can log in with the following credentials:

```
username: agency
password: travel2020
```

**As a travel agent, upon logging in:**
- I should see a dashboard page that shows me:
    - New trip requests (a user's "pending" trips)
    - Total income generated this year (should be 10% of user trip cost)
    - Travelers on trips for today's date (number, names, however you want to display this!)

**As a travel agent:**
- I should be able to see and approve / deny trip requests
- I should be able to search for any user by name and:
    - View their name, a list of all of their trips, and the total amount they’ve spent (including 10% agent cut)
    - Approve a trip request for that user
    - Delete an upcoming trip for that user

**Refer to the endpoints table above for *modifying* and *deleting* a single trip**

## Testing
You should be testing the correctness of your code throughout your project. Each JavaScript class file in your project should have its own test file.

Your testing suite should test all of the functionality of the application, including the following:

* Class default properties
* Class methods
* Anything that updates class properties

## Workflow
You will want to submit PRs to your accountabilibuddy to:

* You must give your accountabilibuddy collaboration access to your repo.
* You must submit _at least_ 2 PRs to your accountabilibuddy for review.
* You must wait for your accountabilibuddy to review your PRs, and allow THEM to merge any PRs you submit.

It is up to you to decide what changes warrant a PR – remember we want to submit PRs that have significant changes and potential for feedback. Think about what functionality you’re struggling with or have questions about or need help with. As an accountabilibuddy, you are responsible for reviewing at least 2 PRs from your partner.

**Please also tag your project manager in any PR you make to your buddy.**

## Extensions
- The user dashboard should display a countdown to my next trip (if I have any)
- Allow the travel agent to POST suggestedActivities for user trips (see Endpoints table above). This could be based off of a user's "travelerType" value.
- Allow the travel agent to create new destinations (see Endpoints table above)
- Utilize an npm package (example: momentJS) - requires permission from instructors
- Choose your own extension! 

## Due Date

Make sure you turn in your project [here](https://forms.gle/dTjaDmgDog9U8dGn6){:target='blank'} by **Tuesday, January 19th at 9pm**

# Rubric

## Specification Adherence

* 4: The application completes all iterations above and implements one or more of the extensions.
* 3: The application completes the first 3 iterations above without error.
* 2: The application completes the first 2 iterations and is in a usable state, but has some miscellaneous bugs.
* 1: The application completes only the first iteration, displaying the user's data, but has no additional functionality.

## UI/UX & Accessibility

* 4: Application has clearly had special consideration around accessibility and usability on devices. Lighthouse accessibility audit is at a 100%.
* 3: Application has many strong pages/interactions. The application can stand on its own to be used by instructor without guidance. The application is fully responsive and the UI does not detract from the UX. Lighthouse accessibility audit is at least 90%.
* 2: The application may be confusing or difficult to use at times.  The UI is incomplete, and the app is not responsive. Accessibility has been considered, but does not have strong accessible features. 
* 1: Application is confusing or difficult to use. The UI is incomplete, and the app is not responsive. Accessibility has not been considered. 

## JavaScript Style & OOP

* 4: Application has exceptionally well-factored code with little or no duplication.  The business-logic code driving functionality is cleanly separated from rendering, view-related code.   Excellent usage of `fetch` and updates DOM based on results of network requests.  Handles all scenarios for error handling.
* 3: Application is thoughtfully put together with some duplication.  Application is organized into classes with some misplaced logic. Business-logic code is mostly separated from view-related code.  Great usage of `fetch` and updates DOM based on results in most scenarios, but may update DOM before a network request is complete.  Handles some scenarios for error handling.
* 2: Class methods use a mix of array and object prototypes and for loops. Application runs but the code has long methods, unnecessary or poorly named variables, and needs significant refactoring.  Uses `fetch` effectively for `GET` but does not implement `POST`.  Has zero error handling and only `logs` errors if a network request fails.
* 1:  Application generates syntax error or crashes during execution.  Application is not separated into classes and there is no separation of business-side logic and view-related code. Developer writes code with unnecessary variables, operations, or steps that do not increase clarity.

## SASS

* 4: Application fulfills all requirements previously mentioned, and has SASS functionality that goes above and beyond an MVP.
* 3: The application has well-factored SASS with all styles separated out into logical stylesheets. Mixins or extends, variables, (appropriate) nesting and color functions have been utilized well.
* 2: Application adds organization for the whole stylesheet and within rules, but multiple SASS files have not been utilized. All SASS code lives in a single file, and only makes use of variables. There is some duplication in the codebase, and there may be some unnecessary selectors or tags. 
* 1: The application makes little to no use of SASS and is not separated into logical stylesheets. There are many instances of duplication

## Testing

* 4: Application covers all aspects of the application including various flows and covers both happy/sad paths.
* 3: Application is well tested but fails to cover some features and only tests for happy paths.
* 2: Project has sporadic use of tests at multiple levels. The application contains numerous holes in testing and/or many features are untested.
* 1: There is little or no evidence of testing in the application.