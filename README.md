# Zarva Backend

## Description

This repository contains the backend for Zarva, an application focused on finding the safest and fastest routes for cars, bikes, and walking. The backend provides API endpoints to calculate these routes, taking into account factors like population density to determine a safety score.

## Features

- **Optimal Route Calculation:** Finds the fastest and safest routes based on the selected mode of transportation (car, bike, or walking).
- **Safety Score:** Calculates a safety score for a given route based on population density.
- **Multiple Transportation Modes:** Supports route calculation for cars, bikes, and pedestrians.

## Prerequisites

- **Node.js:** It is recommended to use the latest LTS version of Node.js.

## Getting Started

To get a local copy up and running, follow these simple steps.

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/zarva-backend.git
    ```
2.  **Install NPM packages:**
    ```sh
    npm install
    ```
3.  **Create a `.env` file:**
    - Create a `.env` file in the root of the project and add the necessary environment variables. You can use the `.env.example` file as a template.
4.  **Start the server:**
    ```sh
    npm run dev
    ```

## Environment Variables

To run this project, you will need to add the following environment variables to your `.env` file:

| Variable        | Description                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------- |
| `PORT`          | The port on which the server will run. The default is `3000`.                                            |
| `OSM_API_KEY`   | Your API key for the OpenRouteService API.                                                                |
| `GEO_API_KEY`   | Your API key for a geocoding service, such as OpenCage.                                                   |
| `SCORE`         | The safety score threshold for a route to be considered safe.                                           |
| `MAP_BOX_API`   | Your API key for the Mapbox Directions API, used for car route calculations.                             |

## API Endpoints

The following API endpoints are available:

-   `POST /v1/api/carRoute`
    -   **Description:** Calculates the fastest route for a car.
    -   **Request Body:**
        ```json
        {
          "origin": "Origin address",
          "destination": "Destination address"
        }
        ```
-   `POST /v1/api/bikeRoute`
    -   **Description:** Calculates the safest and fastest route for a bike.
    -   **Request Body:**
        ```json
        {
          "origin": "Origin address",
          "destination": "Destination address"
        }
        ```
-   `POST /v1/api/walkRoute`
    -   **Description:** Calculates the safest and fastest route for walking.
    -   **Request Body:**
        ```json
        {
          "origin": "Origin address",
          "destination": "Destination address"
        }
        ```
