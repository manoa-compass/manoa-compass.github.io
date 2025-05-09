# Introduction

Manoa Compass is an application that allows users to:

* Register their UH Account.
* Create a user profile that details their major and event interest categories.
* Look at filtered events catered to their selected interests and major chosen by AI.

The problem we hope to solve with this application is the lack of awareness most students have about the events going on around campus. It's easy to just search up all the events happening around campus, but it can take forever to actually find ones that suit your interests and career path. Therefore, we want to make it easier for students to find specific events that meet their interests with our AI-integrated website.

## Build Status
[![ci-nextjs-application-template](https://github.com/manoa-compass/manoa-compass-code/actions/workflows/ci.yml/badge.svg)](https://github.com/ics-software-engineering/nextjs-application-template/actions/workflows/ci.yml)

## Technologies

To implement this website, we will be using various useful tools such as:

* **React** for component-based UI implementation and routing
* **React Bootstrap** for CSS Framework and UI Design
* **Gemini API** for event classifications and alignment with users

## Goals
As mentioned previously, our priority for this application is to create an event hub catered to students to help them get more involved with the events going on around campus whether they be social or career driven based on their interests and major. Our AI of our choosing will be used to understand the content of event descriptions, classify the event in terms of interest areas, ingest the event information into the events database and identify if the event that aligns with the interests is already specified in user profiles. The ability to view other events similar to, or outside of their liking, will be given too if students feel adventurous. If time permits, we also hope to incorporate notifications via email or text messaging to improve the quality of the service. Furthermore, we would also love to add a feedback function for users to make on events they've attended so other students can get an idea beforehand of how other students enjoyed them. 

# Mockup Pages

## Landing Page
The landing page is a simplistic yet user-interactive format with a similar layout to the one you see below. The NavBar will contain the other pages that go to the user's profile, events and clubs, or their dashboard showing all their chosen events.

<img src="imgs/landing.png">

## Sign Up
Our sign-up page will not only prompt the user for their email and a chosen password, but will also ask what their major, interests, name, age, etc. are to gather necessary information for the AI to match events/clubs to the user.

<img src="imgs/mile2step2.png">
<img src="imgs/mile2step3.png">
<img src="imgs/mile2step4.png">
<img src="imgs/mile2step5.png">

## Profile Page
The profile page should include a picture of the student and a list of their selected interest categories for events. The basic information that comes with a profile page is the username, email, major, interests, age range, origin town, comfort level, and an about me section. It also features the saved events and clubs that the user is a part of/wants to attend.

<img src="imgs/mile2profile.png">

## Browse Page
On this page, students will have the option to look through their AI-chosen clubs, all of the clubs currently in the UH Manoa Campus Events Calendar, or get clubs chosen for them. We plan to implement a similar formatted page for events as well.

<img src="imgs/browsepage.png">

## Event Suggestion Page
The event suggestion page will suggest different events to attend based on your interests, along with other events that have a small overlap if you want to try something new. Clicking on one of the cards will either take you directly to the event page, or a custom event information page if we have time.

<img src="imgs/event_suggestion.png">
<img src="imgs/club_suggestion.png">

## Admin Page
Here the admin has the ability to confirm or deny clubs and events, create new ones, and delete and edit existing ones.
<img src="imgs/admin_manage_clubs.png">
<img src="imgs/admin_manage_events.png">
<img src="imgs/edit_events.png">
They can also edit the existing categories and promote other users to admin level. 
<img src="imgs/add_category.png">
<img src="imgs/edit_users.png">
The final thing they can do is run the web scraping scripts by pressing either button. They will also run automatically once a day.
<img src="imgs/admin_scraping.png">
## Club and Event Information Pages
On these pages you can learn more about the event, including key details such as a summary of what it is, when, where, and times for activities. These will only be fully implemented if we have finished the base app.

<img src="imgs/event-info.png">
<img src="imgs/event-info-2.png">
<img src="imgs/club-info.png">
<img src="imgs/club-info-2.png">

# Team Contract
The team contract we all agreed upon can be viewed [here](https://docs.google.com/document/d/113gzfztCkZ03NJD8yignc65mnAk4yQBYTuVxveX-wl4/edit?tab=t.0)

# Deployment 

[Link to Manoa Compass in Vercel](https://manoa-compass-code-theta.vercel.app/) 

# Milestone 1: Mockup Development

The goal of Milestone 1 was to create a set of HTML pages providing a mockup of the pages in the system.

Milestone 1 was managed using [Manoa Compass GitHub Project Board Milestone 1:](https://github.com/orgs/manoa-compass/projects/1)

<img src="imgs/finmilestone1.png">

# Milestone 2 : Backend Development + AI Research

The goal of Milestone 2 is to make our website's backend for each page functionally correct and to dive into scraping the UH events and clubs in the school. Furthermore, one person will be dedicated to testing the AI and researching on how we can implement its functionality into our project.

Milestone 2 was managed using [Manoa Compass GitHub Project Board Milestone 2:](https://github.com/orgs/manoa-compass/projects/2)

<img src="imgs/Milestone2.png">

# Milestone 3: AI Integration and Finishing Touches
In Milestone 3 we worked on integrating the Gemini API to suggest events and clubs to users based on their profiles. We also worked on miscellaneous tasks that had been neglected so far such as finishing the navbar, creating robust tests, and allowing users to save events.

Milestone 3 was managed using [Manoa Compass GitHub Project Board Milestone 3:](https://github.com/orgs/manoa-compass/projects/4)
<img src="imgs/Milestone3.png">
# Project Schema

This is a flow of our project Schema, linking the user, club, and event attributes to the necessary components that allow our website to function as desired. 

<img src="imgs/our_schema.png">

## Community Feedback
Overall the testers thought our app worked well and could be useful for people to find events they may want to attend on campus. However the major criticism was that the loading times are really long, especially for the Suggestions page. Unfortunately this is kind of unavoidable with the gemini free api as you are limited in the amount of requests you can send per minute to only 15 and if you send to many at once it doesnt respond, so we have to space them out and the page takes around 30 seconds to load. To address this we implemented a caching feature where after opening the page one time it will save the returned lists for a few minutes giving quick access. The thing they like the most was the UI and the sign up process, they thought it was very polished and good looking.
## Developer Guide

Welcome to the developer guide for the Manoa Compass project! This guide will walk you through setting up your development environment, running the application, and understanding the codebase for modification and contribution.

### Prerequisites

Before you begin, ensure you have the following installed on your system:

* **Node.js:** (Version specified in `package.json`, if available, otherwise use a recent LTS version)
* **npm** or **yarn:** Package manager for Node.js.
* **Git:** For version control.
* **A database compatible with Prisma:** (e.g., PostgreSQL, MySQL). Check `src/lib/prisma.ts` and potentially `prisma/schema.prisma` (not provided) for specifics.

### Getting Started

Follow these steps to get the project running locally:

1.  **Download the Code:**
    * Clone the repository using Git:
        ```bash
        git clone [https://github.com/manoa-compass/manoa-compass-code](https://github.com/manoa-compass/manoa-compass-code)
        cd manoa-compass-code
        ```

2.  **Installation:**
    * Install project dependencies using npm or yarn:
        ```bash
        npm install
        # or
        yarn install
        ```

3.  **Configuration:**
    * **Environment Variables:** Create a `.env` file in the root directory. Copy the contents of `.env.example` (if available) or add the necessary environment variables. Based on the code, you'll likely need:
        * `DATABASE_URL`: Your database connection string (used by Prisma).
        * `NEXTAUTH_SECRET`: A secret key for NextAuth.js. Generate one using `openssl rand -base64 32`.
        * `GOOGLE_CLIENT_ID`: Your Google OAuth Client ID.
        * `GOOGLE_CLIENT_SECRET`: Your Google OAuth Client Secret.
        * *(Potentially others based on project needs)*
    * **Database Setup:**
        * Ensure your database server is running.
        * Generate Prisma Client:
            ```bash
            npx prisma generate
            ```
        * Push the schema to your database (this creates or updates tables):
            ```bash
            npx prisma db push
            ```
            *(Note: For production or collaborative environments, consider using `prisma migrate dev`)*

### Running the Application

* Start the development server:
    ```bash
    npm run dev
    # or
    yarn dev
    ```
* Open your web browser and navigate to `http://localhost:3000` (or the port specified in your console).

### Key Features & Modules

* **Authentication:** Handled by NextAuth.js, supporting Google OAuth and Email/Password credentials. Password hashing uses bcrypt.
* **Database:** Prisma is used as the ORM to interact with the database.
* **User Profiles:** Users can sign up, manage their profile information, interests, and change passwords.
* **Clubs & Events:** Functionality exists for managing and viewing clubs and events, including admin approval workflows and RSVP capabilities.
* **Recommendations:** An API endpoint provides recommendations based on user interests.
* **Admin Features:** Includes importing data and approving content.
* **Styling:** Uses CSS files, likely leveraging frameworks like Tailwind CSS or Bootstrap based on the HTML mockups and class names.

### Modifying the Code

* **Frontend:** Modify React components and pages within `src/app/`. Update styles in `src/app/globals.css` or relevant CSS Modules.
* **Backend:** Modify API logic in the corresponding files under `src/app/api/`.
* **Database Schema:** If you need to change the database structure, edit `prisma/schema.prisma` and run `npx prisma generate` and `npx prisma db push` (or `npx prisma migrate dev`).
* **Shared Logic:** Update utility functions or configurations in `src/lib/`.
