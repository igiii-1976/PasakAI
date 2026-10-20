# PasakAI

## An IoT-based Jeepney Stop Person Counter

CS 145 Capstone Project

The PasakAI Jeep/Bus Stop Person Counter is an IoT-powered crowd counting system that leverages computer vision to measure crowd count/density at Jeep transportation stops. By using the recent Ultralytics YOLOv11 model capable of object detection, our system will regularly capture images via connected cameras, detect and count people, and send the data to a server. This information will be visualized on a web app interface to guide commuters and drivers in real time, allowing both parties to make informed decisions regarding crowd density at transport stops.

## Screenshots / App preview

<div align="center">
  <img width="300" alt="image" src="https://github.com/user-attachments/assets/5e768020-5937-49e3-bea6-24e8e166e58a" />
  <img width="350" alt="image" src="https://github.com/user-attachments/assets/ff09179d-13fc-4300-bf07-ab82315ac97a" />
</div>

## Features

- Real-time crowd counting and estimation within a certain area in a jeep terminal
- Visualization of crowd density data over time on a web interface
- Historical data tracking to identify peak hours and congestion trends, which is beneficial for drivers, commuters, and policy-makers to improve urban transportation
- Crowd levels based on the displayed count:
  - **Low:** fewer than 5 people
  - **Moderate:** 5–9 people
  - **High:** 10 or more people

## System Architecture

<img width="1015" height="486" alt="image" src="https://github.com/user-attachments/assets/78b20ac9-d60c-4f56-bf6e-35dd29a41415" />
<img width="1240" height="205" alt="image" src="https://github.com/user-attachments/assets/88a1bfc8-4297-40bf-85d3-accac69c4b1f" />

## Installation and setup

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

The project uses SvelteKit's `adapter-auto`. Run `npm run build` to create a production build. If your deployment platform needs a specific output target, choose and configure the corresponding SvelteKit adapter.

## Project team

- Luigi Cumabig
- Karlo Domingo
- Kharis Arielle Ann Hipe
- Kathleen Jocson
- Jeezer Lee
- Harold Andrei Macalisang
- Sebastian Yunque
