# Changelog - Sia's Admin Panel

## [6.0.0] - 2026-02-20

---

### 🔐 Security

- Implemented **UserID-based authorization system**
  - Server-side validation in 'AdminService.lua'
  - Server-side validation in 'BanService.lua'
  - Client-side UI guard in 'SAP.lua'
- Only authorized UserIDs can:
  - Open the admin panel
  - Execute moderation actions
  - Ban users (online & offline)
- Prevents exploiters from firing RemoteEvents manually.

---

### 🔇 Moderation Improvements

- Fully reworked **Mute System**
  - Mutes now completely disable the chat input bar for the affected user.
  - Uses 'ChatInputBarConfiguration.Enabled = false (client-side, targeted).
  - No unreliable TextChatService hacks.
  - Unmute restores full chat functionality.
 
- Added **moderation notifications**
  - Targeted players receive a toast notification when:
    - Teleported
    - Brought
    - Frozen / Unfrozen
    - Muted / Unmuted
  - Displays executing admin name.
  - Includes notification sound.
  - Queued system prevents overlap.

---

### 🔨 Offline Moderation

- Added **Offline Ban system**
  - Ban users without them being in-game at all.
  - Uses Roblox 'BanAsync()' API.
  - Configure:
    - Duration (seconds or permenanet)
    - Display reason
    - Private reason
    - Alt-account flag
  - Status feedback displayed inside panel.
 
---

### 🔎 Offline Player Lookup

- Added **Username → UserID lookup tool**
  - Search users not currently in the game.
  - Displays:
    - Username
    - UserID
    - Group membership
    - Group rank
  - "Use for Ban" button autofills the Offline Ban fields (for the lazies :3).
  - UserID field is selectable (TextBox, read-only) and copyable.

---

### 📢 Announcement System

- Added **Server-wide Announcement feature**
  - Dedicated ANNOUNCE tab.
  - Custom message input.
  - Duration control (clamped server-side).
  - Accent color selection.
  - Displays full-width banner at top of screen.
  - Announcement text is centered.
  - Displays executors/admins name (server-validated).
  - Includes dedicated announcement sound.

---

### 🎨 UI Overhaul

- Modernized Ban Management UI.
  - Rounded corners.
  - Consisent padding.
  - Now matches offline ban styling.
- Improved Player Lookup layout spacing.
- Improved tab navigation structure.
- Panel is now **draggable via header** (Windows-styled behavior).
  - Click & drag title bar to move UI around your screen.
  - Screen clamped (cannot drag off-screen).
  - Works with mouse & touch (mobile-friendly).
 
---

### 🔊 Audio Enhancements

- Toast notification sound added.
- Dedicated announcement sound added.
- Clear distinction between moderation actions and announcements.

### 🧱 Architecture Improvements

- RemoteEvents structured cleanly in Studio:
  - 'AdminRemote'
  - 'BanRemote'
  - 'NotifyRemote'
  - 'MuteRemote'
  - 'AnnounceRemote'
  - 'LookupRemote'
- Authorization checks centralized per service file.
- Server always validates executor identity (no client spoofing).

---

## 🎯 Summary

Version 6.0.0 marks the transition of SAP from a simple admin panel to a structured moderation framework with:

- Secure authorization
- Offline moderation
- Modern UI
- Real-time notifications
- Server-wide announcements
- Improved architecture

This is the largest structural update to SAP so far. Thanks for reading!
