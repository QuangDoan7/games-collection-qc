# Games Collection - Requirements Analysis

## 1. System Overview

Games Collection is an application that allows users to manage a personal collection of video games through a RESTful API.

## 2. Functional Requirements

### REQ-GAME-001 - Retrieve Game by ID

The system shall allow users to retrieve an individual game by its ID through the RESTful API.

Method: GET
Endpoint: /api/:id

### REQ-GAME-002 - Retrieve All Games

The system shall allow users to retrieve all games from the collection through the RESTful API.

Method: GET
Endpoint: /api

### REQ-GAME-003 - Add Game

The system shall allow users to add a new game to the collection through the RESTful API.

Method: POST
Endpoint: /api

### REQ-GAME-004 - Edit Game

The system shall allow users to modify the information of an existing game through the RESTful API.

Method: PUT
Endpoint: /api/:id

### REQ-GAME-005 - Delete Game

The system shall allow users to delete an existing game in the collection through the RESTful API.

Method: DELETE
Endpoint: /api/:id

### REQ-GAME-006 - Delete All Games

The system shall allow users to delete all games in the collection through the RESTful API.

Method: DELETE
Endpoint: /api

## 3. Validation Requirements

### REQ-VAL-001 - Game Name Required

A game name is required when adding a new game.
The game name must not be empty.

### REQ-VAL-002 - Release Year

The Release Year must contain numeric data when provided.

## 4. Open Questions

- Can two games have the same name?
- Can multiple existing games be updated to have the same name?
- Are all game information fields optional?
- Is a release year later than the current year allowed?
