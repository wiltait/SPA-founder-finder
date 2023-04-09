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