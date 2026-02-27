# SAP v0.8.0 - Action Grid Expansion

## 🧩 UI Enhancements (SAPUI.lua)

### ➕ New Quick Action Buttons

The quick action grid has been expanded to a full **3×3 layout** with three new moderation actions:

- 💀 **Kill** (dark red)
- 🔄 **Respawn** (cyan)
- 💚 **Heal** (green)

All three buttons:

- Fire `AdminRemote:FireServer("Kill" / "Respawn" / "Heal", selectedPlayerId)`
- Are fully integrated into `applyRoleVisibility()`
- Automatically hide based on role permissions

### 📐 Layout Adjustment

- `actionButtonsFrame` height increased from **80px → 126px**
- Grid now cleanly supports three full rows
- Layout spacing adjusted to preserve visual balance

---

## 🛠 Backend Implementation (AdminService.lua)

Three new branches were added inside `AdminRemote.OnServerEvent`:

### 💀 Kill
- Locates target `Humanoid`
- Sets `Health = 0`
- Sends toast notification
- Prints server log entry

### 🔄 Respawn
- Calls `targetPlayer:LoadCharacter()`
- Sends toast notification
- Prints server log entry

### 💚 Heal
- Sets `humanoid.Health = humanoid.MaxHealth`
- Sends toast notification
- Prints server log entry

All actions:

- Include formatted role tag (e.g. `[Owner] sia`)
- Trigger server-side output logging

---

## 🔐 Permission Updates (PermissionService.lua)

Added new permission flags to role definitions:

- `Kill`
- `Respawn`
- `Heal`

### Role Access Matrix

| Role        | Kill | Respawn | Heal |
|------------|------|----------|------|
| Owner      | ✅   | ✅       | ✅   |
| Manager    | ✅   | ✅       | ✅   |
| Admin      | ✅   | ✅       | ✅   |
| Moderator  | ✅   | ✅       | ✅   |
| TrialMod   | ❌   | ❌       | ✅   |

**Design decision:**  
Trial Moderators are restricted from destructive actions but may use healing, as it is considered non-punitive.

All permissions remain fully server-enforced.

---

## 🔔 NotificationService.lua Updates

Added three new toast types:

- 💀 **Kill** - dark red styling  
- 🔄 **Respawn** - cyan styling  
- 💚 **Heal** - green styling  

Example:
You were healed by [Owner] sia.

All toasts use formatted role display and consistent color-coded feedback.
