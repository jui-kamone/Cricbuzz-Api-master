# Cricbuzz

Introducing a Role-Based Access Control system designed for two distinct roles: Admin and User. Users can view match information, while Admins have the additional capability to manage match and player details.

## Table of Contents

<img width="1234" alt="Screenshot 2024-05-19 at 2 34 31 PM" src="https://github.com/jui-kamone/Cricbuzz-Api-master/assets/118176425/5c955542-ece1-416e-ae09-6c63b9ed6296">



- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)

## Installation

This system is built on the Django framework with Postgres as the underlying database.

To get started, install the necessary packages:

Install the dependencies

```
pip install -r requirements.txt
```


Configure the dbsettings schema in app/schemas.py according to the PGAdmin details of your Postgres DB.

Run init__db.py to create Tables in DB:
```
python init_db.py
```

Run the project using uvicorn

```
    uvicorn main:app --reload
```

Run add_data.py to add some basic data:

```
python add_data.py
```

API Endpoints
Here's a breakdown of the available API endpoints:


Guest Accessible Endpoints:


1
```
GET /api/matches:
     Retrieves a list of upcoming matches.
```


2
```
GET /api/matches/{match_id}:
     Retrieves details of a specific match by its ID, including the players in the squads.
```



Admin Accessible Endpoints
Note: Admin API endpoints are protected by Token Authentication. 
To access these endpoints, include the Authorization header with the value "Bearer {Token}".

Admin Authentication

3
```
POST /api/admin/signup:
     Allows Admin registration.
```

4
```
POST /api/admin/login:
     Enables Admin login. Upon successful authentication, a token is provided for further requests.
```



Matches
5
```
POST /api/matches:
     Creates a new match by providing required parameters.
```


6
```
POST /api/teams/{team_id}/squad:
      Adds players to a team's squad.
``` 


7
```
POST /api/players/{player_id}/stats:
    Retrieves statistics of a player by their ID.
``` 



8
```
POST /api/players/addplayer:
     Adds new players to the database.
``` 






