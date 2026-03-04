# WebRTC IP Leak - Privacy Research Tool

### ⚠️ Educational Purpose Only
This project is created for **educational and research purposes only**. It demonstrates how the WebRTC protocol can inadvertently leak a user's public IP address even when behind certain layers of abstraction. 
**Do not use this script on platforms or users without explicit permission.**

---

## 📋 Overview
WebRTC (Web Real-Time Communication) uses the **ICE (Interactive Connectivity Establishment)** framework to find the shortest path between two peers. 

During this "handshake," the browser generates **ICE Candidates**. Some of these candidates, specifically the `srflx` (Server Reflexive) type, are retrieved from STUN servers and contain the user's **Public IP Address**.

## 🚀 How It Works
The script performs a "Monkey Patch" (hook) on the native `RTCPeerConnection` API:
1. It intercepts the `addIceCandidate` method.
2. It parses the candidate string to find the public IP.
3. It uses a Geolocation API (`ipinfo.io`) to fetch metadata about that IP.
