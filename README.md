# Photon VR Multiplayer Template


![metaverse (2)](https://github.com/user-attachments/assets/c036c703-7729-4fd4-b9b3-7ff4d3c1c5b5)



This Unity project is a **multiplayer VR template** built with **Photon PUN 2**, **XR Interaction Toolkit**, and **Photon Voice**. It allows multiple players to connect in a shared VR environment, interact with each other, and manipulate objects in real-time, with the added ability to communicate via real-time voice communication.

---

## 🚀 Features

- 👥 **Multiplayer VR Avatars**  
  Synchronizes head and hand positions of each player over the network.

- ✋ **Hand Presence and Animations**  
  Hand models reflect real-time trigger and grip inputs from VR controllers.

- 🎮 **Networked Object Interaction**  
  Objects can be picked up and interacted with using XR Grab Interactables, and ownership is transferred over the network.

- 📡 **Simple Lobby and Room System**  
  Automatically connects to Photon server and joins or creates rooms with predefined settings.

- 🔊 **Real-Time Voice Communication**  
  Photon Voice enables real-time voice communication between players in the network, enhancing the multiplayer experience.

---

## 📁 Scripts Overview

### `NetworkManager.cs`
Handles the connection to the Photon server, joins the lobby, and allows creation/joining of rooms with predefined settings.

### `NetworkPlayer.cs`
Maps the local player's XR Rig (head and controllers) to a networked avatar and updates hand animations. Disables local avatar rendering to avoid overlapping visuals.

### `XRGrabNetworkInteractable.cs`
Extends XRGrabInteractable to request object ownership through Photon when a player grabs an item, allowing proper sync in multiplayer.

### `HandPresence.cs`
Initializes the correct hand model or controller prefab depending on the connected device. Also updates hand animations based on input data.

---

## 🧱 Prefabs

### `NetworkPlayer` Prefab

The `NetworkPlayer` prefab is the main representation of each player in the networked VR space. It includes:

- Head and hand tracking (via `NetworkPlayer.cs`)
- Hand model animations
- PhotonView for synchronization
- Photon Voice for real-time voice communication

Make sure this prefab is registered under **PhotonNetwork.Instantiate** in your spawn logic so that each player has a synchronized avatar and voice communication on join.

---

## 🧪 Quick Start

### ✅ Requirements
- Unity 2020.3 or newer
- XR Interaction Toolkit
- Photon PUN 2
- Photon Voice
- OpenXR Plugin (or relevant VR SDK)

### 🔧 Setup
1. Clone this repository.
2. Open the project in Unity.
3. Set up your XR Plugin Management and input actions.
4. Add your Photon App ID under **PhotonServerSettings**.
5. Hit play and test in multiplayer!

> If you don't want to manually set up the scene, simply open the **`Assets/Scenes/Lobby.unity`** for a ready-to-use setup.

---

