# SAP - Sia's Admin Panel

> A modern, secure and structured moderation framework built specifically for ROBLOX experiences.

SAP (Sia's Admin Panel) is a lightweight yet powerful administration system designed for serious developers who care about security, clean architecture, and official moderation integration.

Unlike traditional admin scripts, SAP is built as a structured moderation framework - not a collection of improvised commands.

---

# 💖 What is SAP?

SAP provides real-time player management, secure ban handling, offline moderation tools, and a clean, modern interface - all while integrating directly with Roblox's official moderation infrastructure.

It is designed to:

- Avoid DataStore-based ban systems
- Avoid exploitable RemoteEvent structures
- Avoid cluttered, outdated admin UI designs
- Feel official, professional, and production-ready

---

# 🔒 Official Roblox Ban Integration

One of SAP's core strengths is its ban management system.

Unlike many admin tools (such as Adonis or Kohl's Admin) that store bans in DataStores or local systems, SAP uses **Roblox's official Ban API**.

This means:

- ✅ Bans are stored directly in your game's official moderation system
- ✅ Fully visible and manageable inside the Creator Hub
- ✅ No custom DataStore ban lists
- ✅ No unofficial bypass risks
- ✅ Cleaner, safer and more professional moderation

With SAP, you never need to manually open the Creator Hub to manage bans - everything is handled directly through Roblox's official infrastructure.

---

# ✨ Core Features (v6.0.0)

## 🔐 Secure Authorization System
- UserId-based admin validation
- Server-side executor verification
- RemoteEvent protection against spoofing
- Client UI guard for unauthorized users

---

## 🔨 Advanced Ban Management
- Online bans
- Offline bans (ban users not in-game)
- Permanent or timed bans
- Display reason & private reason
- Alt-account flag support
- Uses `BanAsync()` officially

---

## 🔇 Mute System
- Fully disables chat input for muted players
- Clean restore on unmute
- Server-validated execution
- Target receives moderation notification

---

## 📢 Server-wide Announcement System
- Dedicated announcement tab
- Custom message input
- Configurable duration
- Accent color selection
- Displays executor name (server-validated)
- Dedicated notification sound
- Clean full-width banner UI

---

## 🔎 Offline Player Lookup
- Username → UserId lookup
- Works without player being in-game
- Displays:
  - Username
  - UserId (selectable & copyable)
  - Group membership
  - Group rank
- Autofill ban fields directly from lookup result

---

## ⚡ Real-Time Player Management
- Bring
- Teleport
- Freeze / Unfreeze
- Spectate
- Kick
- Instant moderation feedback

---

## 🔔 Moderation Notifications
- Targeted toast notifications
- Shows executing admin name
- Queued to prevent overlap
- Separate sounds for:
  - Moderation actions
  - Announcements

---

## 🎨 Modern UI
- Clean, rounded design
- Structured tab navigation
- Draggable window (Windows-style behavior)
- Screen-bound movement
- Touch and mouse support

---

# 🧱 Architecture Philosophy

SAP is structured into modular systems:

- AdminService
- BanService
- MuteService
- Announcement system
- Lookup system
- Notification system

RemoteEvents are separated and validated as well.

All critical moderation logic is validated server-side.

SAP is built to feel like a framework - not a script.

---

# 🚀 Roadmap

SAP is now feature-complete in terms of core moderation systems.

The only planned addition:

## 🔗 Discord Integration
- Moderation log webhook support
- Optional Discord bot integration
- Server-side logging of moderation actions
- Structured log formatting for communities

No additional in-game moderation systems are currently planned.

Future updates will focus on:
- Stability
- Optimization
- Refinement
- Security improvements

---

# 🎯 Project Vision

SAP is not meant to compete with legacy admin systems.

It is built for developers who want:

- Official moderation integration
- Clean architecture
- Secure execution
- Professional UI design
- Structured development practices

The goal is simple:

> Make moderation feel official, structured, and safe - not improvised.

---

# 📜 License

No License (All Rights Reserved).

---

# ❓ Questions?

Check the FAQ channel in the Discord server: https://discord.gg/tma37dSbaP

Sneak peeks and updates are posted regularly.
