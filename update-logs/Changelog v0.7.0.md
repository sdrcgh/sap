# SAP v0.7.0 - Role Infrastructure & Permission System Rewrite

## 🔐 Major: Role-Based Permission System

Introduced a fully centralized permission architecture.

### ➕ Added
- `SAP_Permissions.lua` (ModuleScript, ServerScriptService)
  - Single source of truth for:
    - Role definitions (`ROLES`) 
    - Member assignments (`MEMBERS`)
    - Permission matrix
  - All services now `require()` this module
  - Static `AUTHORIZED_ADMINS` system fully removed

Example member assignment:
```lua
[1636521366] = "Owner",
[987654321]  = "Moderator",
```

## 📊 Default Permission Matrix

| Action                               | Owner | Manager | Admin | Mod | Trial |
|---------------------------------------|--------|----------|--------|------|--------|
| Teleport / Bring / Freeze / Kick     | ✅     | ✅       | ✅     | ✅   | ❌     |
| Mute / Spectate / Lookup             | ✅     | ✅       | ✅     | ✅   | ✅     |
| Ban (Online)                         | ✅     | ✅       | ✅     | ❌   | ❌     |
| Offline Ban Tab                      | ✅     | ✅       | ❌     | ❌   | ❌     |
| Announce                             | ✅     | ✅       | ✅     | ❌   | ❌     |

All permissions are now enforced server-side via:

- `Permissions.isStaff()`
- `Permissions.canDo()`

---

## 🔄 Service Refactors

### AdminService.lua

- Removed `AUTHORIZED_ADMINS`
- Now validates actions via permission module

On `PlayerAdded`:

- Fires `RoleRemote`
- Sends:
  - Role name
  - Role colour
  - Chat tag
  - Allowed actions table

All notifications now pass formatted role display.

Example: [Owner] sia

---

### BanService.lua

- Now uses `Permissions.canDo(admin, "Ban")`
- Fully permission-gated online banning

---

### NotificationService.lua

- Removed hardcoded `"Admin "` prefix
- Notifications now use formatted role display

Example: [Owner] sia muted you.

---

## 🖥 SAPUI Refactor

### Role-Based UI Enforcement

- Replaced `AUTHORIZED_ADMINS` logic
- UI now waits (max 10 seconds) for `RoleRemote`
- Non-staff users are silently halted

`applyRoleVisibility()`:

- Hides buttons the role cannot use
- Hides entire tabs (Offline Ban / Announce) if not permitted

---

## 🆕 Settings Tab

- Added new ⚙ **Settings** tab
- Chat Tag toggle moved here
- Prepared for future expansion of configurable options

---

## 💬 Chat Tag Toggle

- Off by default
- Enables/disables colored `[Role]` prefix in chat
- Uses `TextChatService.OnIncomingMessage`
- Fully role-colour integrated

---

## ❌ Removed

- Overhead role tag system completely removed
  - `BillboardGui` logic deleted
  - Toggle button removed
  - All related listeners cleaned up

---

## 🐛 Bug Fixes

- Fixed `applyRoleVisibility()` nil indexing crash
  - Function previously referenced UI elements before they were created
  - Reordered initialization to guarantee variable existence
- Fixed Offline Ban and Announce tabs not being clickable
- Resolved console error: attempt to index nil with 'Visible'


---

## 📡 New RemoteEvent

- Added `RoleRemote` (ReplicatedStorage)
- Required for role synchronization between server and client

---

## 🧠 Architectural Impact

SAP is now a fully role-driven moderation framework.

- Centralized permissions
- Server-enforced authority
- Role-based UI visibility
- Structured tab-level access control

This update removes static admin lists and transitions SAP into a scalable, production-ready moderation infrastructure.
