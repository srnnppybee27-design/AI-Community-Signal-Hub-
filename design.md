# MeshReach AI – System Design Document

## 1. System Overview

MeshReach AI is an offline first mobile application that distributes civic information through a local WiFi sync hub. The system ensures access to essential information even without internet connectivity.


## 2. High Level Architecture

Government/NGO Data Sources
        ↓
Admin Device (Internet Optional)
        ↓
Local WiFi Sync Hub
        ↓
User Mobile Devices
        ↓
Offline Database + AI Assistant


## 3. System Components

### 3.1 Mobile Application
- User Interface (UI)
- AI Assistant Module
- Local Database (SQLite)
- Sync Manager
- Notification System

### 3.2 Local Sync Hub
- Local WiFi hotspot
- Update server ( Node.js)
- Stores latest data package

### 3.3 Admin Module
- Uploads updated JSON data files
- Maintains version control


## 4. Data Flow

1. Admin uploads updated civic data.
2. Sync hub stores latest data package.
3. User connects to community WiFi.
4. App checks version number.
5. If new version exists → downloads update.
6. Local database is updated.
7. AI assistant uses updated data.


## 5. Database Design

Example Table: CivicInfo

- id (Primary Key).
- title.
- category.
- description.
- eligibility.
- deadline.
- location.
- priority.
- last updated.

Data stored locally using SQLite.

## 6. AI Assistant Design

### Input:
- Text or Voice query

### Processing:
- Intent detection
- Keyword matching
- Category filtering

### Output:
- Relevant information
- Text response
- Text to Speech output


## 7. Update Synchronization Process

- App sends current version to sync hub.
- Hub compares version.
- If new version available:
- Sends updated data file.
- App updates local database.
- Confirmation message shown.

## 8. Security Considerations

- Data package validation.
- Version control system.
- No personal user data required.
- Local encrypted storage.

## 9. Scalability Considerations

- Can deploy multiple sync hubs.
- Data stored in modular format.
- Supports expansion to multiple regions.
- Multi language support scalable.


## 10. Technology Stack

Mobile App:
- Flutter/Android (Kotlin)

Backend (Sync Hub):
- Flask/Node.js

Database:
- SQLite (Mobile)
- JSON data packages

AI Module:
- Lightweight NLP engine
- Offline speech recognition
- Text to Speech API


## 11. Future Enhancements

- Bluetooth mesh sync integration.
- AI based recommendation engine.
- Cloud integration when internet available.
- Real time emergency broadcasting.
