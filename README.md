# SPA Founder Finder: Building a Single Page Application with Third-Party API Integration
This is a minimal Single Page Application (SPA) that displays information about company founders. It fetches demographic data from https://randomuser.me/, an avatar from https://robohash.org/, and the company they founded from https://fakerapi.it (under companies).

## Prerequisites
* Node.js v12 or higher (to check your version, run `node -v` in a terminal)

## Getting Started
To run this project on your local machine, please follow the steps below:

1. Clone this repository to your local machine using one of the following ways:
Download the ZIP file of this repository and extract its content to your local machine.
Use the following command in a terminal:

`git clone https://github.com/wiltait/SPA-founder-finder.git`

2. Open a terminal and navigate to the root directory of the project.

3. Install the project dependencies by running the following command:

`npm install`

4. Run the project by executing the following command:

`npm run serve`

5. Once the server is running, open your web browser and navigate to http://localhost:8080/ (unless your terminal specifies a different port).

6. Enter a founder ID (any character will do) to retrieve information about the founder. The SPA will fetch deterministic data from the 3rd party APIs mentioned above, based on the provided founder ID.


## Project Structure
This project is built using Vue.js, but you are free to use any other technology you like. The structure of this project follows the basic Vue.js configuration using the Vue-CLI.

* `App.vue`: This is the main component that renders the background and the CompanyFounder component.
* `CompanyFounder.vue`: This component is responsible for fetching the founder data and rendering the FounderProfile component.
* `FounderProfile.vue`: This component is responsible for rendering the fetched founder data.






# bh-dev-assessment

## Assignment

We'd like you to create a very minimal SPA "company founders" page, based on some dummy data fetched from 3rd party APIs.

You should fetch:
- The founder's demographic data from https://randomuser.me/
- The founder's avatar from https://robohash.org/
- The company they founded from https://fakerapi.it (under companies)

All three APIs allow for deterministic data generation so your SPA should deterministically return the same data based on the same "founder ID" provided by the user.

In terms of technology to use, we use Vue but feel free to use whatever you want to get things up and running as quick as possible. We've set up this repo with as simple Vue structure as possible, but please make as many changes as you'd like or just start from scratch.

Don't bother spending too long styling it, we're more interested in how you architect the page/components/requests than making it look too pretty (although feel free to use something like [Vuetify](https://vuetifyjs.com) or some flavour of [Bootstrap](https://dev.bootstrap-vue.org/) to get things off the ground if that's easier). Feel free to include as much or as little data from the APIs as you would like but use your judgement about what would be useful to highlight on a profile page dedicated to company founders.


## Expectations

Please make use of version control as you go along so we get a little bit of insight into how you iteratively approach this. However we would appreciate it if you did not publish this assessment on public repositories so we can reuse this assessment in the future. Please send us back the zipped up git/mercurial repository.

We expect you to spend around 2-3 hours on this assessment, however you are welcome to spend more time if you feel that will help you to demonstrate your skills better (but please don't spend too long, we appreciate a good work-life balance).


## Project setup

We've set this up with Vue/npm using a basic Vue-CLI configuration. Please keep this section updated if you make modifications.

To get started you should run `npm install`, then you might want to try:

- Compiles and hot-reloads for development: `npm run serve`
- Compiles and minifies for production: `npm run build`
- Lints and fixes files: `npm run lint`