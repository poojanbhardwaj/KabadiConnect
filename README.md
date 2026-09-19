# KabadiConnect

KabadiConnect is an end-to-end e-waste collection and recycler coordination platform developed by **Team WhiteFoxAlliance** for **Smart India Hackathon 2026**.

The platform aims to connect informal e-waste collectors with formal recyclers through a structured workflow for lot creation, offer discovery, offer acceptance, transaction tracking, handover, and payment visibility.

---

## Problem

Informal e-waste collectors have strong last-mile reach, but they often face problems such as:

- Limited access to formal recyclers
- Difficulty comparing offers and prices
- Uncertain pickup and handover processes
- Lack of structured transaction records
- Poor or unstable internet connectivity during field work

KabadiConnect is designed to bridge this gap without replacing the existing collector ecosystem.

---

## Solution

KabadiConnect provides two connected interfaces:

### Collector Mobile App

A Flutter-based mobile application for informal collectors.

Collectors can:

- Create e-waste lots
- Select material category and condition
- Enter approximate weight and expected value
- Add location and images
- Store lots locally before synchronization
- Sync lots when connectivity is available
- Receive recycler offers
- Accept or reject offers
- View transactions
- Track handover records
- View payment-related status

### Recycler Web Platform

A React-based web application for recyclers.

Recyclers can:

- Discover available e-waste lots
- View lot details
- Submit offers
- Track offer status
- View accepted transactions
- Follow handover information
- Access shared lot and transaction records

---

## Architecture

```text
Collector Flutter App
        |
        v
Node.js Collector Gateway
        |
        v
Go Canonical API
        |
        v
MongoDB
        ^
        |
React Recycler Web Platform
```

### Architecture Overview

The system follows a shared-domain architecture.

- The **Flutter app** is the collector-facing mobile client.
- The **Node.js gateway** handles collector-facing API compatibility and media-related requests.
- The **Go backend** acts as the canonical authority for shared business data.
- **MongoDB** stores the shared domain records.
- The **React web application** provides the recycler-facing interface.

The Go backend is the primary shared-domain writer for:

- Users
- E-waste lots
- Offers
- Transactions
- Handovers
- Payments
- Price records

---

## Core Workflow

```text
Collector creates an e-waste lot
        ↓
Lot is stored locally
        ↓
Lot is synchronized
        ↓
Recycler discovers the lot
        ↓
Recycler submits an offer
        ↓
Collector accepts or rejects the offer
        ↓
Transaction is created
        ↓
Handover is tracked
        ↓
Payment status can be viewed
```

---

## Tech Stack

### Mobile

- Flutter
- Dart
- SQLite

### Frontend

- React
- TypeScript

### Backend

- Go
- Node.js
- TypeScript

### Database

- MongoDB

### Development and Infrastructure

- Docker
- Git
- GitHub

---

## Key Features

- Offline-first collector workflow
- Local lot storage and later synchronization
- E-waste lot creation
- Recycler marketplace
- Recycler offer creation
- Collector offer acceptance and rejection
- Duplicate-safe transaction creation
- Transaction tracking
- Handover tracking
- Recycler discovery
- Price board
- Shared canonical backend architecture
- Collector and recycler authentication
- Retry-safe synchronization flows

---

## E-Waste Categories

The current platform supports categories such as:

- CRT
- LCD Panel
- PCB
- Cable
- Battery
- Motor
- Magnet-bearing Assembly
- Mixed Plastics from electronic/electrical equipment
- Other E-Waste

---

## Current Status

The project currently has a **working end-to-end prototype**.

### Validated Locally

- Collector app can create e-waste lots
- Lots can be synchronized
- Recycler website can discover synchronized lots
- Recycler can submit offers
- Collector can view offers
- Collector can accept or reject offers
- Accepted offers can create transactions
- Collector and recycler flows communicate through the shared backend
- Core backend and API contract tests have been performed

### In Progress

- Production deployment
- Production authentication hardening
- Production media storage
- Field validation
- Final lifecycle refinements
- Real-world pilot testing

This repository is a public project showcase.

The active development and integration repository is maintained separately.

---

## Screenshots

Screenshots of the complete workflow will be added here.

Planned screenshots include:

1. Collector home screen
2. Create e-waste lot screen
3. Synced e-waste lot
4. Recycler marketplace
5. Recycler offer screen
6. Collector offer acceptance/rejection screen

---

## Team

Developed by **Team WhiteFoxAlliance**, a 6-member team for **Smart India Hackathon 2026**.

Individual team member contributions are documented in:

[CONTRIBUTORS.md](CONTRIBUTORS.md)

---

## Project Context

**Project:** Kabadiwala Connect

**Problem Statement:** Bringing the Informal Collector into the Formal Recycling Chain

**Theme:** Clean & Green Technology

**Category:** Software

---

## My Contribution

### Poojan Bhardwaj

My work on the project includes:

- System integration
- Recycler website integration
- Go canonical backend integration
- Collector-to-recycler API integration
- End-to-end workflow testing
- Debugging cross-platform data flow
- Validating Collector → Node.js → Go → MongoDB → React communication
- Offer and transaction workflow integration

---

## Why This Project Matters

KabadiConnect does not aim to remove informal collectors from the e-waste ecosystem.

Instead, the goal is to preserve their strong last-mile collection network while providing a digital bridge to formal recyclers.

The platform is designed to improve:

- Access to recycler offers
- Transaction visibility
- Handover traceability
- Payment visibility
- Formal recycling participation

---

## Future Scope

Future work may include:

- Production deployment
- Real recycler onboarding and verification
- Improved vernacular support
- Audio-assisted workflows
- Production-grade media storage
- Enhanced payment tracking
- Field pilot validation
- Data-driven price recommendations after sufficient real-world data is collected

---

## Disclaimer

KabadiConnect is currently a prototype under active development.

The following are **not currently claimed as complete production capabilities**:

- Production deployment
- Government recycler verification integration
- Real-world payment processing
- Large-scale field adoption
- Production-scale user traffic
- AI-based price prediction

The project is being iteratively improved based on testing and validation.
