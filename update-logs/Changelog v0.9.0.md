# SAP v0.9.0 - UI Redesign & Theme System (03/02/2026)
*Final update before SAP v1.0.0*

This update introduces a **complete visual redesign of the SAP interface**, alongside a **new theme system** and several UI improvements.  
All functionality and moderation systems remain unchanged - this update focuses on **presentation, usability, and UI architecture**.

---

# 🎨 Complete UI Redesign

The entire **SAPUI.lua** interface has been rebuilt to follow a modern **pastel design system** inspired by the SAP branding.

The new UI introduces:

• Softer pastel color palette  
• Frosted-glass panel styling  
• Improved layout spacing  
• Distinct tab color accents  
• Consistent card-style UI elements  
• Structured visual hierarchy

The redesign improves readability, usability, and overall visual clarity.

---

# 🧊 Frosted Panel System

The main admin panel now uses a **semi-transparent frosted background** to blend subtly with the Roblox environment.

Features include:

• Light frosted panel transparency  
• Soft depth effect  
• Floating panel appearance  
• Improved visual separation from the game world

---

# 🌑 Theme System

SAP now supports multiple UI themes selectable from the **Settings tab**.

## Available Themes

### Pastel (Default)

The new standard theme featuring:

• Soft pastel UI colors  
• Color-coded action buttons  
• Role-friendly moderation interface  
• Frosted UI panels

### Dark

A darker, minimal interface variant designed for low brightness environments.

### Legacy

A nostalgic recreation of the **original SAP UI**.

Features:

• Classic grey interface  
• Flat UI design  
• Original button colors  
• Traditional Roblox admin aesthetic

This allows people who liked the old design better to keep the **classic SAP look**.

---

# 🎨 Tab Accent Colors

Each major tab now uses its own accent color when active:

| Tab | Accent Color |
|----|----|
| Players | Soft Sky Blue |
| Offline Ban | Soft Purple |
| Announce | Soft Amber |
| Settings | Soft Sage Green |

Inactive tabs remain neutral for better visual focus.

---

# 🧩 Action Button Visual Improvements

All moderation actions now have **distinct functional pastel colors**:

| Action | Color |
|------|------|
| Bring | Teal |
| Teleport | Sky Blue |
| Spectate | Amber |
| Freeze | Periwinkle |
| Mute | Lavender |
| Kick | Orange |
| Kill | Coral Red |
| Respawn | Cyan |
| Heal | Mint Green |

This makes actions **instantly recognizable at a glance**.

---

# 🪟 Panel & Layout Improvements

The admin panel now includes:

• Improved spacing across all UI sections  
• Clear separation between sidebar and content panels  
• Rounded interface elements  
• Structured input fields  
• Cleaner button grid alignment

The panel also now includes a **floating shadow layer** to create depth.

---

# 🏷 Header & Logo Section

The header now includes a dedicated **SAP logo area**.

Layout:

• **SAP Logo**  
• Title: `SIA'S ADMIN PANEL`  
• Version label next to the title  

This improves branding and visual identity.

---

# ⚙ Settings Tab Improvements

The **Settings tab** now contains the **Theme Switcher**.

Users can toggle between:

• Pastel  
• Dark  
• Legacy

Future SAP configuration options will also be added here. In the future, Settings will also be saved, even after relogging/leaving and not only for the session.

---

# 🛠 UI Fixes

### Removed Panel Glow

A blue glow effect appearing around the admin panel has been fixed.

Cause:

`UIStroke` on the outer panel caused visual bleed outside the frame.

Fix:

The outer panel stroke was removed while keeping inner UI strokes intact.

---

# 🧹 Code Cleanup

• Removed unused `mainStroke` references  
• Cleaned up UI registry references  
• Improved theme switching logic  
• Ensured consistent UI element initialization

---

This update prepares the project for the upcoming **SAP v1.0.0 release**. Stay tuned in #sneak-peeks! :3
