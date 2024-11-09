# Volleyball Team Management

A web app to help volleyball coaches and players manage teams. This tool allows coaches to add players, assign positions, track stats, schedule games, and enable players to RSVP for games.

## Features

- Add and manage players with specific positions
- Track game schedules and team lineup
- RSVP to scheduled games
- View and manage past game data

## Project Structure

- Folder structure:
  ```bash
  volleyball-team-management
  ├── client
  │ ├── src
  │ │ ├── components
  │ │ │ ├── PlayerForm.js
  │ │ │ ├── TeamList.js
  │ │ │ ├── PlayerCard.js
  │ │ │ ├── GameSchedule.js
  │ │ │ └── RSVPButton.js
  │ │ ├── pages
  │ │ │ ├── TeamPage.js
  │ │ │ └── SchedulePage.js
  │ │ ├── App.js
  │ │ └── index.js
  │ ├── public
  │ └── package.json
  └── server
  ├── controllers
  │ ├── playerController.js
  │ ├── teamController.js
  │ └── scheduleController.js
  ├── models
  │ ├── User.js
  │ ├── Team.js
  │ ├── Player.js
  │ ├── Game.js
  │ └── RSVP.js
  ├── routes
  │ ├── teamRoutes.js
  │ └── scheduleRoutes.js
  ├── config
  │ └── database.js
  └── server.js
  ```

## React Components

- **PlayerForm**: Form for adding/editing player details
- **TeamList**: Displays team roster
- **PlayerCard**: Shows player stats and position
- **GameSchedule**: Lists upcoming games
- **RSVPButton**: Allows players to RSVP for games

## API Endpoints

| Method | Endpoint                | Description             |
| ------ | ----------------------- | ----------------------- |
| POST   | /api/teams              | Create a new team       |
| GET    | /api/teams/:teamId      | Retrieve team details   |
| POST   | /api/players            | Add a new player        |
| GET    | /api/players/:playerId  | Get details of a player |
| POST   | /api/games              | Schedule a new game     |
| GET    | /api/games/:gameId      | Retrieve game details   |
| POST   | /api/games/:gameId/rsvp | RSVP for a game         |

## Database Tables & Relationships

- **Users**: Stores user details (id, name, email)
- **Teams**: Stores team details (id, coach_id, team_name)
- **Players**: Stores player details (id, team_id, name, position, jersey_number)
- **Games**: Stores game details (id, team_id, date, opponent)
- **RSVPs**: Stores RSVP details (id, game_id, player_id, status)

Each `Team` has a `User` as the coach, each `Player` belongs to a `Team`, each `Game` is associated with a `Team`, and each `RSVP` is associated with a `Game` and `Player`.

## Installation

1. Clone the repository
2. Install dependencies for the client and server:

```bash
cd client && npm install
cd ../server && npm install
```

3. Configure database in server/config/database.js
4. Start the development servers:
   ```bash
   cd server && npm run dev
   cd client && npm start
   ```
