# Liar's Dice
A gambling game following the rules as established in [Pirates of the Caribbean: Dead Man's Chest.](https://www.youtube.com/watch?v=T44LuxdH0iw) 

## Technologies To Be Used
- SvelteKit - for frontend and backend API
- MongoDB - for backend database
- Solidity - after MVP, to implement real currency and allow players to use their wallet address to play

## Models

### User
- username: String (unique)
- password: String
- loggedIn: Boolean
- wallet: Number (to be replaced by crypto wallet address)
- currentGame: Number (nullable) - represents gameId
- gameData: Object
    - roll: Array of Numbers - representing rolled dice, with the length of the array being number of dice that decreases over the course of the game
    - call: Array of Numbers
        - Number - representing the quantity dice being called
        - Number - representing the face value of the dice being called
- gameStats: Object (post MVP)
    - wins: Number
    - defeats: Number
    - profits: Number
    - losses: Number

### Game
- gameId: Number
- gameAlias: String
- gameSize: Number
- bettingPool: sum of money paid by players to be sent to victor
- turn: Number
- turnOrder: Object of Strings - dictionary of ennumerated usernames in game
- turnPlayer: Number

## Router Route Table

| Route | URL | API | Description |
| ----- | --- | --- | ----------- |
| Index | `/` |     | Landing page to show game premise |
| Create | `/signup` | `/signup` | POST new User |
| Login | `/login` | `/login/:id` | GET User then PUT loggedIn |
| Show | `/lobby/[:gameId]` | `/lobby/[:gameId]` | GET Game(s) or POST new Game |
| Update |  | `/play/:username` | PUT User and Game as needed |
| Account | `/account` | `/account/:username` | PUT User.loggedIn or DELETE User |

## Components
- Navbar
- Main
- Form
- Dice
- Player (to visually represent other players and their public gameData)
- Chat (post MVP)

## Pages
- Landing
- Signup
- Login
- Lobby (out of game, see other games to join or spectate)
- Table (when in game)
- Account (logout, delete account, view other players' info)

## Tree
```
App
 |_____ Main
```

## User Stories


## Development Notes
