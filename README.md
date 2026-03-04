# WebRTC IP Leak - Privacy Research Tool

### ⚠️ Educational Purpose Only
This project is created for **educational and research purposes only**. It demonstrates how the WebRTC protocol can inadvertently leak a user's public IP address even when behind certain layers of abstraction. 
**Do not use this script on platforms or users without explicit permission.**

---

## 📋 Overview
WebRTC (Web Real-Time Communication) uses the **ICE (Interactive Connectivity Establishment)** framework to find the shortest path between two peers. 

During this "handshake," the browser generates **ICE Candidates**. Some of these candidates, specifically the `srflx` (Server Reflexive) type, are retrieved from STUN servers and contain the user's **Public IP Address**.

---

## 🛠️ Usage
To test this script in a controlled, educational environment:

1. **Clone this repository** to your local machine.
2. **Open a website** that uses WebRTC (e.g., P2P video chats or WebRTC leak test sites).
3. **Open the Browser Console** by pressing `F12` and selecting the **Console** tab (or `Ctrl+Shift+I`).
4. **Paste the content** of `script.js` into the console and press `Enter`.
5. **Logs will appear** automatically in the console whenever a peer connection is established and an IP is identified.

## 🛡️ How to Protect Yourself
To prevent this type of leak and maintain your privacy:

* **Use a high-quality VPN:** Ensure your VPN provider specifically masks WebRTC traffic (not all do by default).
* **Install browser extensions:** Use tools like **WebRTC Leak Prevent** or **uBlock Origin** (with WebRTC blocking enabled).
* **Firefox Configuration:** You can disable WebRTC entirely by typing `about:config` in the address bar and setting `media.peerconnection.enabled` to `false`.

## ⚖️ License
Distributed under the MIT License. See `LICENSE` for more information.
