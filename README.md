<p align="center"><a href="#" onclick="alert('Project is not deployed')" target="_blank"><img src="https://i.ibb.co/k266Mg9/logo.png" width="400" alt="Nexus Logo"></a></p>

<p align="center">
<h2 align="center">Nexus</h2>
<h3 align="center">Take-Home Challenge FullStack</h3>
</p>

## About The Project

This project is a take-home challenge for the FullStack web developer position. In this challenge a news aggregator website has been built that pulls articles from various sources(for example: NewsAPI, The Gurdian and The New York Times) and display them in a clean, easy-to-read format. It has been tried to give it a name and a logo as Nexus and it includes two separate projects:

- **[Nexus API](https://github.com/rislam169/nexus-api)** The backend of the application
- **[Nexus Frontend](https://github.com/rislam169/nexus-news)** The frontend of the application

Both application(frontend and backend) is connected as submodules with this repository and has possibility to run both application from this main module.

## Installation Process

Both application is Dockerized, so [Docker](https://docs.docker.com/get-docker/) is required and a pre-requisite of this application. You can check by running `docker info` or any docker command to check if docker is running or not.

### 1. Clone The Repository

```
git clone --recurse-submodules git@github.com:rislam169/nexus-project.git
```

### 2. Change current directory to working directory

```
cd nexus-project/
```

### 3. Start and run the application

```
docker compose up -d --build
```

This process might take some time to install all the dependency and setup the containers. If there is no issue, and no earthquake outside, containers will run in detach mode and project should be available at http://127.0.0.1:3000 or http://localhost:3000.

### 4. Running Scheduler (Optional)

In order to import the articles daily from the article providers,there is a scheduler which runs everyday at 06.00 in the morning. Below command will run the scheuler.

```
docker exec -it <nexusApi-containerId> crond -f
```

## Current Workflow

Currently the system is pulling the articles from News API, The Gurdian and The New York Times while system boots up. Besides that, it pulls new articles from the providers everyday in the morning.

Visitors of the application can read the artilces in a clean and eay to read format. Besides that, Users are able to search for articles by keyword and filter the results by date, category, and source. To improve the search experience and having a blazing fast result, [meilisearch](https://www.meilisearch.com/) has been taken into action in separate container and implemented in the project through laravel scout.

Not only that, users are able to customize the news feed by selecting their preferred sources, categories, and authors in profile. Users should log in first to get the access to the profile. The customized news feed only availble for the users who already signed up and logged in. Last but not least, The frontend is responsive and accessible from smaller devices.
