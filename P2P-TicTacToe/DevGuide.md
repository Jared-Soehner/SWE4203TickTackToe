# Developer Documentation for Tic-Tac-Toe Game

## Introduction

Welcome to the developer documentation for the Tic-Tac-Toe game project. This documentation aims to provide comprehensive insights into the system architecture, APIs, and development workflow.

## System Overview

The Tic-Tac-Toe game is a client-server application built using Java. It follows a client-server architecture where clients interact with the server via HTTP requests.

### Components:

- **Server**: Handles game logic, manages game sessions, and serves API endpoints.
- **Client**: Provides a graphical user interface (GUI) for players to interact with the game.

## Server Architecture

The server is responsible for coordinating game sessions, managing player moves, and enforcing game rules. It utilizes Java's `com.sun.net.httpserver` package for handling HTTP requests.

### Components:

- **Main**: Entry point for the server application. Initializes the HTTP server and sets up request handlers.
- **GameManager**: Manages game sessions, player connections, and game state.
- **Handlers**: Handle incoming HTTP requests and route them to appropriate game actions.

## REST API

The server exposes a RESTful API for various game actions such as starting a game, making moves, and joining game sessions.

### API Endpoints:

- `POST /api/start-server`: Start a new game session.
- `GET /api/search-for-game`: Search for an existing game session.
- `GET /api/join-as-host`: Join a game session as a host.
- `GET /api/join-as-opponent`: Join a game session as an opponent.
- `GET /api/move`: Make a move in the game.

## Client Architecture

The client provides a graphical interface for players to interact with the game. It communicates with the server via HTTP requests to perform game actions.

### Components:

- **GUI**: Displays game board, player actions, and game status.
- **HTTP Client**: Sends HTTP requests to the server API endpoints.

## Development Workflow

To contribute to the project or make modifications, follow these steps:

1. Clone the project repository.
2. Install Java and ensure JDK is set up properly.
3. Use `javac` to compile the source files.
4. Run the server using `java Main`.
5. Open the client interface and start playing or making changes as needed.

## Swagger Documentation

The project includes a Swagger YAML file (`swagger.yml`) for API documentation. You can visualize and explore the API endpoints using Swagger tools.