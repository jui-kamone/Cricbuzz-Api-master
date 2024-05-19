# Table of Contents

- [Cricbuzz](#cricbuzz)
  * [DataBase Design Concept](#database-design-concept)
  * [Installation](#installation)
  * [API Endpoints](#api-endpoints)


# Cricbuzz API Mock

Introducing a Role-Based Access Control system designed for two distinct roles: Admin and User. Users can view match information, while Admins have the additional capability to manage match and player details.


## DataBase Design Concept

<img width="1234" alt="Screenshot 2024-05-19 at 2 34 31 PM" src="https://github.com/jui-kamone/Cricbuzz-Api-master/assets/118176425/5c955542-ece1-416e-ae09-6c63b9ed6296">

## Installation

To get started, follow the given instructions:

### Install the dependencies

```
pip install -r requirements.txt
```


Configure the dbsettings schema in ```app/schemas.py``` according to the PGAdmin details of your Postgres DB.

### Create Tables in Database:

```
python init_db.py
```

### Run the project using uvicorn

```
    uvicorn main:app --reload
```

### Run add_data.py to add some basic data:

```
python add_data.py
```

## API Endpoints
API endpoints implemented:

#### Public Endpoints (Open to anyone):

1. ```GET /api/matches:``` - Gives the list of upcoming matches.

2. ```GET /api/matches/{match_id}:``` - Gives the detail of a specific match with the players in the squads.

### Private Endpoints (Admin only):

>    Include the Authorization header with the value "Bearer {Token}" in your request.

3. ```POST /api/admin/signup:``` - SignUp

4. ``` POST /api/admin/login:``` - LogIn

>    Use the token returned after login for further requests.

5. ``` POST /api/matches:``` -  Creates a new match.
6. ``` POST /api/teams/{team_id}/squad:``` - Adds players to a particular team. 
7. ``` POST /api/players/{player_id}/stats: ``` - Stats of a player.
8. ```POST /api/players/addplayer: ``` - Adds new players.






