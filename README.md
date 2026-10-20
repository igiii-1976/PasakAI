# PasakAI

A CS 145 Capstone Project

## Project team

- Luigi Cumabig
- Karlo Domingo
- Kharis Arielle Ann Hipe
- Kathleen Jocson
- Jeezer Lee
- Harold Andrei Macalisang
- Sebastian Yunque
- Team 17

PasakAI is a SvelteKit dashboard for viewing estimated passenger counts at selected locations around the UP Diliman campus. Stop cards show a count, crowding level, address, update time, and current w[...] 

## Features

- Live passenger-count updates for the AECH Lobby from Firebase Cloud Firestore.
- Sample passenger snapshots and historical averages for other campus stops.
- Current weather from the Open-Meteo forecast API.
- Crowd levels based on the displayed count:
  - **Low:** fewer than 5 people
  - **Moderate:** 5–9 people
  - **High:** 10 or more people

## Data and limitations

- **AECH Lobby:** Reads updates from the Firestore `aechLobby` collection.
- **AECH Conference, Vinzons Hall, AECH, Area 2, and Krus na Ligas:** Use hardcoded sample snapshots and averages in `src/lib/prevStopsData.ts`; these are not live counts.
- **Weather:** Requested from Open-Meteo using the coordinates in `src/lib/weather.ts`.

Counts and update times are only as current as their source. In particular, data for locations other than AECH Lobby is sample data and may be out of date.

## Getting started

### Requirements

- Node.js (current LTS recommended)
- npm

### Install and run

```sh
npm install
npm run dev
```

Open the local URL printed by Vite, usually `http://localhost:5173`.

## Available commands

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server. |
| `npm run build` | Build the production app. |
| `npm run preview` | Preview the production build locally. |
| `npm run check` | Run Svelte and TypeScript checks. |
| `npm run lint` | Check formatting with Prettier and run ESLint. |
| `npm run format` | Format project files with Prettier. |

## Firebase configuration

Firebase is initialized in `src/lib/firebase.ts` with a web app configuration embedded in the source. To connect a fork to another Firebase project, use that project's web app configuration and make s[...] 

Firebase web configuration is visible to clients and is not an authorization boundary. Use Firebase Security Rules to control access to your data.

## Project structure

```text
src/
  lib/
    components/
      BarChart.svelte    Historical averages chart
      Header.svelte      Dashboard header
      HourlyAvg.svelte   Stop details and chart popup
      JeepStop.svelte    Stop card
    firebase.ts          Firebase and Firestore initialization
    helpers.ts           Time and data aggregation helpers
    prevStopsData.ts     Sample location snapshots and averages
    stopaddress.ts       Location address labels
    weather.ts           Open-Meteo request and location parameters
    weathertype.ts       Weather code labels
  routes/
    +layout.svelte       Shared page layout
    +page.svelte         Main stop dashboard
static/                  Images and other public assets
```

## Deployment

The project uses SvelteKit's `adapter-auto`. Run `npm run build` to create a production build. If your deployment platform needs a specific output target, choose and configure the corresponding Svelte[...] 
