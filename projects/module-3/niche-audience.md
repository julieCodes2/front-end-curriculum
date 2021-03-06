---
title: Niche Audience
module: 3
tags: react, javascript, api
---

## Introduction

This project will challenge you to use the technology you've become familiar with over the course of Mod 3, as well as force you to work inside some constraints. Everyone will be working with (at least) one API and one audience.

## Project Goals and Requirements

1. Use the technology you've been working with over the course of the module to
   demonstrate mastery of the following:
   - React
   - Router
   - Asynchronous JavaScript
   - End to end testing with Cypress

2. Create personas and user stories to describe your target audience. 

3. Work within constraints to deliver a product for your niche audience, which helps solve a problem unique to them.

4. Your applications must have the following core functionality:
  - **Display** the data from the API in a way that applies directly to your audience
  - Ability for users to **store/manipulate** the data displayed in the application, such as favoriting or adding to a list, searching, commenting, etc
  - Multiple views handled by Router

## Abstract

This project, having a short time frame, will need to pack a lot into a small space. We're going to accomplish this by building an app that serves the needs of a very small, very niche audience.

You'll create an MVP to serve a deeply specific audience of users.

<section class="answer">
### What is an MVP? 

When we talk about "MVP", we mean "**M**inimum **V**iable **P**roduct"! 

An MVP defines the features that MUST be included in an app to achieve its base, core functionality.

Let's consider Twittter. It's MVP may be defined as:
- A user can write a tweet, which when submitted will be visible on the page

That's it! Obviously, Twitter has MANY more features. But without tweets, Twitter wouldn't be Twitter. 

These other Twitter features (which may FEEL very central and vital) are actually just nice-to-haves, which make the experience richer and more robust:
- A user can log in
- A user can see their previous tweets
- A user can follow another user
- A user can like tweets
- A user can re-tweet
- etc

</section>

## Process

Here are some tips for creating an interesting, tightly-scoped application!

### Finding an API

Choose an open API to work with where the data sounds interesting to you. A good place to start looking is [this repo with a list of free/open APIs](https://github.com/public-apis/public-apis). Choose an API where you could make an application based on the data from the API. _Do not choose an API that requires "OAuth or OAuth 2.0"_, which is a more complicated authentication scheme. Also, be wary of APIs that have "CORS" value of "no."

APIs that require an `apikey` are usually easy to deal with, and some APIs don't require an `apikey`. If the API you want to use relies on an API key, be sure to request one ASAP!

### Choosing an audience

After you have an API that interests you, the next thing you need to do is choose an audience. You need to be **specific** with your audience.

For example, if you chose an API that served cat data, your audience should not just be "cat lovers". Instead, it should be something more specific like "cat lovers who live in Alaska". This will give you some constraints for the project to make it more unique and design decisions a little easier.

**GET WEIRD. HAVE FUN.** (And also still be professional. Silliness is good; rudeness/crassness is not.)

Once you've got your API and audience settled, start thinking about how you're going to build something for this audience, using that API. Come up with a few different ideas.

### Niche audience

The best audiences for this project are highly specific. You won't have a lot of time to build something, so a big app that has to serve lots of different audience members is not really feasible. You're not building Airbnb or Twitter here. 

Examples of past student apps that had excellent audiences:
- An app that interprets sports statistics into bite-sized sentences to share at work, intended to help non-sports-fans talk to sports-fans.
- An app for plant-killers to remember to water their plants.
- An app for wine-haters to find wines to try.
- An app for soon-to-be-dads to begin building up a repertoire of dad jokes.

As you can see, specific, niche audiences are more fun and interesting than broad audiences! These constraints will help inspire specific app features.

## Thinking like a developer

This project is often a portfolio piece for FE students. So let's make this as professional as possible!

### User personas

We expect you to write 2 thorough user personas which describe two members of your niche audience. These personas should inform the design & features/functionality of your app.

### Wireframes & design inspiration

Wireframing will be a major component of this project. The more time you spend intentionally thinking about the layout/views and user flow of your application, the better the final result will be.

There are many different tools you can use for this, including just plain old pen and paper. Just make sure you really spend time thinking about the user interactions. For a good overview of how to effectively wireframe a project, check out [this video](https://www.youtube.com/watch?v=e2Oynq-mOLk).

We also want you to choose two design inspiration pieces, which can be as broad as inspiration for the layout of your app, to as small as a color palette or a micro-interaction animation.

### Day 1 Deliverables

By 3PM of Day 1:

* Create a DM with both instructors
* Send the following:
  - Your niche audience (be as specific and narrow as possible)
  - Your chosen API
  - The information you will be using from it
  - A list of your app's MVP features
  - Optional: a list of your app's nice-to-have features
  - A backup API & audience

Once your project MVP is approved (instructors will help you narrow down your MVP to a reasonable scope), please also send the following:

* Wireframes
* Links to 2 design inspirations
* 2 separate user personas describing people in your niche audience
* Project board link
* Repo link

## Rubric

Remember: scores are an indicator of your progress in specific areas.

Score key:  
- **4:** above and beyond expectations; did extensive self-teaching to achieve
- **3:** right on track; exactly where instructors expect you to be
- **2:** a little behind; be sure to devote study & practice time to this area in order to accelerate growth/understanding
- **1:** very behind; strongly recommend you reach out to instructors to create a plan to catch up in this area

### Specification Adherence

* **4:** 
  - Project meets MVP & adds nice-to-haves; meets all project requirements
* **3:** 
  - Project meets MVP; meets all project requirements
* **2:** 
  - Project either does not meet MVP or does not meet all project requirements
* **1:** 
  - Project does not meet MVP or project requirements

### React Architecture

* **4:**
  - A consistent, modular file structure is used
  - A clear understanding of class components vs function components is demonstrated (if using hooks, a clear understanding of when hooks need to be used is sufficient)
  - Only the data that a child component _needs_ are passed down as props
  - Logic is kept out of `return` statements; `return` statements are as readable as possible, only communicating what will be displayed
  - Fetch calls have been refactored to be reusable for multiple queries
  - Frontend data (state) always matches the backend data
  - Data fetched from API is run through a cleaning function (which is defined in a separate `utilities` file)
  - Implements excellent error handling if movie database server is down or fetch fails (this includes loading images as well as error messages on the frontend)
* **3:** 
  - A consistent, modular file structure is used
  - A clear understanding of class components vs function components is demonstrated (if using hooks, a clear understanding of when hooks need to be used is sufficient)
  - Only the data that a child component _needs_ is passed down as props
  - Logic is kept out of return statements; return statements are as readable as possible, only communicating what will be displayed
  - There are some issues with the asynchronous JS where the frontend is not matching with the backend
  - There are multiple functions (including fetch calls) that are doing similar pieces of functionality that could continue to be refactored
  - Data fetched from API is not cleaned before being set to state
* **2:** 
  - The file structure is inconsistent and/or not modular
  - There is some confusion about when to use a class or function component, but it does not hinder functionality
  - Unnecessary data is passed down to child components as props
  - `return` statements contain logic that should be refactored out for the sake of readability and performance
  - There are methods that are being created inside of functional components that should be passed down through props from a parent class component
  - API calls have not been broken out into their own file
* **1:**
  - Project shows little understanding of React and significant refactoring is required, including but not limited to:
    - component structure is inconsistent or buggy
    - a class component is used when a function component is preferable, and/or vice versa
    - props are being passed or accessed incorrectly
    - props are being mutated
    - state is directly mutated
  - File structure is not modular.

### Project Professionalism

The goal of this rubric section is to continue to gauge your readiness and prepare you for workplace standards. As you ramp up your job hunt, it becomes increasingly important to demonstrate to future employers that you are not sloppy and take care with the details of your work and processes!

* **4:**  
  - README concisely communicates your learning goals, the evolution of the project, and reflections - while using good formatting to enhance readability
  - README links to any applicable repos/deployed sites
  - You use a rebase workflow
  - Git commits are atomic, with concise and precise descriptions of the change made
  - PRs have full, consistent descriptions
  - You lean on cohortmates or a mentor to do consistent, thorough, meaningful code reviews of PRs, which prompt updates and changes made to that PR before merging
  - Evolution of the project (decisions made, etc) is fully and clearly documented in the git history and PRs
  - When the project is run locally, the terminal shows no errors or warnings
  - PropTypes or type-checking of props is complete and specific (all data passed into a component is correctly and specifically identified)
* **3:**
  - README concisely communicates the team's individual and joint learning goals, the evolution of the project, and team member reflections while using good formatting to enhance readability
  - README links to all applicable repos/deployed sites
  - Git commits are atomic, with concise and precise descriptions of the change made
  - PRs have full, consistent descriptions
  - Evolution of the project (decisions made, etc) is documented in the git history and PRs but is sometimes unclear
  - When the project is run locally, the terminal shows no errors and fewer than 5 warnings
  - PropTypes or type-checking of props is mostly complete
* **2:**
  - README concisely communicates your learning goals and the evolution of the project, but does not use Markdown formatting to aid readability
  - README links to any applicable repos/deployed sites
  - Git commits are mostly atomic but sometimes document changesets that are too large
  - PRs do not have thorough descriptions
  - Team members mostly do not do code reviews on PRs
  - Evolution of the project (decisions made, etc) is not clearly documented through git commits and PRs
  - When the project is run locally, the terminal shows no errors and more than 5 warnings
  - PropTypes or type-checking of props is incomplete
* **1:** 
  - README does not document your learning goals, the evolution of the project, and is poorly formatted (hindering readability)
  - README does not include links to team member's GitHub profiles
  - Git commits are not atomic and document changesets that are too large
  - PRs do not have thorough descriptions, and no code reviews are conducted, merging bugs into the main branch
  - When the project is run locally, the terminal shows errors and more than 5 warnings
  - PropTypes or type-checking of props is not implemented

### Testing

* **4:** 
  - Team has successfully achieved 90%+ test coverage of all components
  - All async functionality is mocked
  - Async tests cover happy & sad paths
  - All unit tests are in place, including conditional rendering
  - All integration tests are in place, tested from the correct component
* **3:** 
  - All unit tests are in place & passing, including any conditional rendering
  - All integration tests are in place, tested from the correct component
  - Happy path async functionality is tested
* **2:**
  - Most unit tests are in place & passing
  - A valid attempt is made at integration testing; some integration tests may be in the wrong place (aka, attempted to be done by a component that cannot actually "see"/access all the necessary functionality/data)
  - Little or no attempt at async testing was made
* **1:** 
  - Many unit tests are missing/failing
  - Little or no attempt is made at integration testing
  - Little or no attempt is made at async testing
  - There are obvious, large gaps in testing app functionality

### Routing  

* **4:**
  - Application has been refactored to use Router without leaving artifacts of the prior code (no odd workarounds remaining)
  - Use of Router shows developer empathy (readability, maintainability)
  - Application uses React Router components and does not manipulate the `history` object 
  - A 404 page handles undefined routes
  - UX is excellent; routes are consistent and navigation is clear
* **3:**
  - Application uses Router to display appropriate components based on URL
  - Refactoring was clean; there may be a few code smells showing the existence of the prior code, but there are no major bugs indicating a lack of understanding of Router
  - Application uses React Router components and does not manipulate the `history` object
  - UX is clear and set up so the user has access to previous routes
* **2:**
  - Application uses Router but does not display the appropriate components when navigating throughout the app
  - Refactoring is messy; there are remnants of the previous code or other code smells that indicate that Router is not clearly understood
  - There are 1+ issues with the UX; access to routes is unclear or not fully implemented
* **1:**
  - Application uses Router but fails to properly display all necessary routes
  - Application does not use built-in React Router components and instead directly manipulates the `history` object
  - UX is challenging; multiple pages are missing links to routes, or browser Back/Forward arrow navigation does not work
