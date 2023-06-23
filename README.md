<p align="center"><a href="#" onclick="alert('Project is not deployed')" target="_blank"><img src="https://i.ibb.co/k266Mg9/logo.png" width="400" alt="Nexus Logo"></a></p>

<p align="center">
<h2 style="text-align:center">Nexus</h2>
<h3 style="text-align:center">Take-Home Challenge FullStack</h3>
</p>

## About The Project

This project is a take-home challenge for the FullStack web developer position. In this challenge a news aggregator website has been built that pulls articles from various sources(for example: NewsAPI, The Gurdian and The New York Times) and displays them in a clean, easy-to-read format. I tried to give it a name and a logo as Nexus Project :

- **[Nexus API](https://github.com/rislam169/nexus-api)** The backend of the application
- **[Nexus Frontend](https://github.com/rislam169/nexus-news)** The frontend of the application

Both application(frontend and backend) is connected as submodules with this repository and has possibility to run both application from this main module.

## Installation Process

Both application is Dockerized, so [Docker](https://docs.docker.com/get-docker/) is required and a prerequisite of this application.

### 1. Clone The Repository

```
git clone --recursive-submodules git@github.com:rislam169/nexus-news.git
```

### 2. Change current directory to working directory

```
cd nexus-news/
```

### 3. Start and run the application

```
Run docker compose up --build
```

If there is no issue, and no earthquake outside project should be available at http://127.0.0.1:3000 or http://localhost:3000.

## Current Workflow

Currently the system is pulling the articles from News API, The Gurdian and The New York Times while system boots up. Besides that, it pulls new articles from the providers everyday in the morning.

Visitors of the application can read the artilces in a clean and eay to read format. Besides that, Users are able to search for articles by keyword and filter the results by date, category, and source. Not only that, users are able to customize the news feed by selecting their preferred sources, categories, and authors in profile. The customized news feed only availble for the users who already signed up and logged in. Last but not least, The frontend is responsive and accessible from smaller devices.
