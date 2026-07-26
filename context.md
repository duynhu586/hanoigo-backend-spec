# Social Map + PostGIS Context

## 1. Project Overview

HanoiGO is a travel social networking application.

This module is responsible for implementing the backend of the Social Map feature.

Users can:

- create activities
- discover nearby activities
- join activities
- view activity details

The frontend will consume REST APIs provided by this module.

---

## 2. Scope

This module ONLY includes backend development.

Included:

- Activities CRUD
- Nearby Feed
- Join Activity
- PostGIS queries
- Validation
- Authorization
- API Testing

Not included:

- Mobile UI
- React Native
- Map rendering
- Apple Developer Program
- Push Notification UI

---

## 3. Tech Stack

Framework

- NestJS

Database

- PostgreSQL
- PostGIS

ORM

- Prisma

Authentication

- JWT
- AuthGuard

Testing

- Jest
- Supertest
- Postman

---

## 4. Existing Project Structure

Current module

activities/

Current files

- activities.module.ts
- activities.controller.ts

The controller currently contains only placeholders and needs to be implemented.

---

## 5. Existing Database

The database already exists.

Main tables:

- User
- Activity
- ActivityParticipant
- City

The Activity table stores its location using a PostGIS Point column.

---

## 6. Main Features

This module should provide:

### Activity CRUD

- Create Activity
- Get Activity
- Update Activity
- Delete Activity

---

### Nearby Feed

Nearby activities should be queried using PostGIS.

Main functions:

- ST_DWithin
- ST_Distance

The feed supports:

- radius search
- distance sorting
- participant sorting
- time sorting

---

### Join Activity

Users can join activities.

Business rules include:

- cannot join twice
- cannot join full activity
- activity must exist

---

## 7. Architecture

Client

↓

NestJS Controller

↓

Service

↓

Prisma

↓

PostgreSQL + PostGIS

---

## 8. Development Principles

The implementation follows:

- Clean Architecture
- REST API
- SOLID
- Test Driven Development (TDD)

Every endpoint should have:

- DTO
- Validation
- Service
- Tests

---

## 9. Deliverables

When finished, the module should provide:

✓ Activity CRUD API

✓ Nearby Feed API

✓ Join Activity API

✓ Unit Tests

✓ Integration Tests

✓ Postman Tests

---

## 10. Out of Scope

This module does NOT implement:

- Frontend UI
- Mobile screens
- Native Google Sign-In
- Apple Sign-In UI
- Socket.io
- Push Notification UI

These belong to other project phases.

---

## 11. Working Workflow

Every feature should be implemented in the following order:

1. Read implementation plan
2. Design API
3. Write test cases
4. Implement
5. Run tests
6. Refactor
7. Update documentation

---

## 12. Notes

The implementation plan (`plan.md`) is the source of truth for daily development tasks.

This document only provides project context.

Whenever starting a new task, read this file first, then follow the implementation plan.

## 13. Current Status

Completed

- None

In Progress

- None

Blocked

- Waiting for ...

Next Task

- Setup Activities Module
