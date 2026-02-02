# JamfSupportSnapshot

<p align="left">
  <img src="assets/icon.png" width="200" />
</p>

## 🧭 Support Snapshot

Fast, structured Jamf Pro visibility for frontline IT & Support

Support Snapshot is a lightweight macOS app that pulls real-time Jamf Pro inventory into a single, readable snapshot for support engineers.
It removes the need to jump between Jamf pages, logs, and API calls while troubleshooting devices.

## 🚀 What it does today (Computers)

Support Snapshot currently supports macOS computers via Jamf Pro’s modern API:

| Capability | What you see |
|---|---|
| General | Name, Jamf ID, user, enrollment, MDM status, last check-in |
| Hardware | Model, serial, CPU, RAM, storage, battery |
| Security | SIP, Activation Lock, attestation |
| Applications | Installed app name, version, path |
| Configuration Profiles | Profile name, ID, install date |
| Certificates | Common name, expiration, status |

Everything is presented as a single “support-grade” snapshot instead of scattered Jamf pages.



## 🧩 How it works

Support Snapshot talks directly to Jamf Pro using the modern API:

Computers
/api/v1/computers/{id}/inventory-detail


The app:
- Pulls all computer IDs
- Fetches each full inventory record
- Normalizes it into a Support Snapshot view
- Displays everything in one UI
- No classic API XML. No scraping. No Jamf UI dependency.

## 🔑 Requirements (Jamf API Access)

Support Snapshot uses **Jamf Pro Client Credentials (OAuth)**.  
You must create an API Client in Jamf Pro before using the app.

### Required API Permissions

Your Jamf API Client must have at least:

| Category | Privileges |
|---|---|
| Computers | Read |
| Mobile Devices | Read |

## 🔐 Security

- Uses Jamf Pro Bearer Tokens
- Tokens stay local to your Mac
- No data is stored externally
- No Jamf credentials are saved in the app


## 📱 Mobile Devices (Coming Soon)

Mobile device support is currently in development.
Planned endpoint:
/api/v2/mobile-devices/{id}/detail

When released, Support Snapshot will show:

- Device name, model, iOS version
- Supervision & MDM status
- User assignment
- iCloud & Activation Lock
- Lost Mode, Passcode, Compliance
- Last check-in and inventory
This will give Support teams the same snapshot experience they already have for computers.



## 🛠 Installation

1. Download the latest build from the Releases page.
2. macOS
3. Download the .zip
4. Move Support Snapshot.app to Applications
5. Launch the app
6. Enter your Jamf Pro URL and API token

If macOS blocks it:
System Settings → Privacy & Security → Open Anyway


## 🧠 Why Support Snapshot exists

Jamf has powerful APIs — but frontline support teams shouldn’t have to:

- Build curl commands
- Parse JSON
- Or dig through 10 Jamf pages per ticket

Support Snapshot turns Jamf into a support-grade diagnostic tool.

## 📸 Screenshots
<img src="screenshots/main-view.png" width="48%" />
![Computer Details](screenshots/computer-details.png)

