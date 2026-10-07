# Games Collection - Test Scenarios

## REQ-GAME-001 - Retrieve Game by ID

### TS-001

Verify that an existing game can be retrieved by its ID.

### TS-002

Verify API behavior when retrieving a game using a non-existing ID.

### TS-003

Verify API behavior when retrieving a game using a non-numeric ID.

## REQ-GAME-002 - Retrieve All Games

### TS-004

Verify that all games from the collection can be retrieved.

### TS-005

Verify API behavior when attempting to retrieve all games in an empty collection.

## REQ-GAME-003 - Add Game

### TS-006

Verify that a new game can be successfully added to the collection with all fields populated.

### TS-007

Verify API behavior when adding a new game with at least one field empty.

### TS-008

Verify API behavior when adding a new game with all fields empty.

### TS-009

Verify API behavior when adding a new game with non-numeric data for the Release Year.

## REQ-GAME-004 - Edit Game

### TS-010

Verify that an existing game can be successfully modified with at least one field updated.

### TS-011

Verify that an existing game can be successfully modified with all fields updated.

### TS-012

Verify API behavior when modifying an existing game using non-numeric data for the Release Year.

### TS-013

Verify API behavior when modifying a game using a non-existing ID.

### TS-014

Verify API behavior when modifying a game using a non-numeric ID.

## REQ-GAME-005 - Delete Game

### TS-015

Verify that an existing game can be deleted.

### TS-016

Verify API behavior when deleting a game using a non-existing ID.

### TS-017

Verify API behavior when deleting a game using a non-numeric ID.

## REQ-GAME-006 - Delete All Games

### TS-018

Verify that all games in the collection can be deleted.

### TS-019

Verify API behavior when attempting to delete all games in an empty collection.
