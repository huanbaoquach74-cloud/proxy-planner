# Proxy Planner — Zenless Zone Zero

A lightweight, mobile-friendly build and farming tracker for Zenless Zone Zero.

## Use the app

Open the GitHub Pages site:

https://huanbaoquach74-cloud.github.io/proxy-planner/

1. Enter a ZZZ UID.
2. Press **Đồng bộ** to load the account's public Enka Showcase.
3. Select an Agent from the roster to edit ATK, AP, AM, notes, and farming tasks.
4. Enter another UID to switch profiles. Returning to a UID restores its saved planner data on this browser/device.

## What it reads

- Public Agent Showcase data from Enka.Network: Agent level, Mindscape, Core Skill, W-Engine, and equipped Drive Discs.
- Localized Agent, W-Engine, Drive Disc, and property names from `game-data.json`.

The account owner must make their character details visible in the in-game Showcase. The app never asks for a HoYoverse password, cookie, or login token.

## Data and privacy

- Build stats, notes, checklists, and cached Showcase responses are saved in the browser's local storage.
- Profiles are separated by UID on the same browser/device.
- Data is not synced between devices and is not uploaded to a Proxy Planner account.
- If Enka cannot be reached directly due to browser restrictions, the app attempts public CORS relays. Relay availability is not guaranteed.

## Development notes

This is a static GitHub Pages app. Enka data is fetched on demand and cached according to the API's `ttl` value. The app does not enumerate UIDs or run a server-side UID crawler.

Game metadata is sourced from Enka.Network's parsed ZZZ data. Verify game-specific calculations separately before using the app as a build optimizer.
