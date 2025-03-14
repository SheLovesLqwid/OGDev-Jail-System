
# **OGDev-Jail-System**  
A **FiveM jail system** that integrates with [EasyAdmin-Ox](https://github.com/crazy-kol/EasyAdmin-OxLib), allowing authorized staff members to **jail and unjail players** with permission-based controls.  

⚠ **Note:** *I am not the original creator of EasyAdmin-Ox. Full credit goes to its developer. My script simply extends its functionality by adding a jail system.*  

---

## **📌 Features**  
- 🔹 Jail players for a set duration with EasyAdmin commands  
- 🔹 Unjail players manually or automatically when time expires  
- 🔹 Staff role-based permissions for jail management  
- 🔹 Works with **ESX, QBCore, and standalone servers**  
- 🔹 Configurable **jail locations, cells, and escape prevention**  
- 🔹 Optimized and lightweight for performance  

---

## **📂 Installation**  

### **1️⃣ Download & Install**  
1. **Download** the latest version from GitHub.  
2. Extract the folder and rename it to `OGDev-Jail-System`.  
3. Place it inside your **FiveM resources folder** (`server-data/resources/`).  

### **2️⃣ Dependencies**  
Ensure the following dependencies are installed and running:  
- [EasyAdmin-Ox](https://github.com/crazy-kol/EasyAdmin-OxLib) (Required for admin commands)  
  - *I am not the creator of EasyAdmin-Ox. Full credit to the original developer.*  
- [OxLib](https://overextended.dev/) (For UI and permissions)  

### **3️⃣ Add to Server Config**  
Open `server.cfg` and add:  
```ini
ensure EasyAdmin-Ox
ensure OGDev-Jail-System
```

---

## **⚙️ Configuration**  

Edit `Config.lua` inside `OGDev-Jail-System` to customize jail settings.  

### **Jail Locations**  
Define jail positions and cells:  
```lua
Config.JailLocations = {
    {x = 1776.82, y = 2505.25, z = 45.80}, -- Main jail
    {x = 1782.3, y = 2490.4, z = 45.8},   -- Cell 1
    {x = 1786.5, y = 2492.8, z = 45.8}    -- Cell 2
}
```

### **Staff Permissions**  
Specify roles that can use jail commands:  
```lua
Config.AllowedStaff = {
    "admin",
    "moderator",
    "superadmin"
}
```

### **Escape Prevention**  
Prevent jailed players from leaving the area:  
```lua
Config.PreventEscape = true -- Set to false to disable
```

---

## **🚀 Commands**  

| Command | Description | Usage |  
|---------|------------|--------|  
| `/jail [ID] [Time]` | Jails a player for a set time | `/jail 23 10` (10 minutes) |  
| `/unjail [ID]` | Releases a player from jail | `/unjail 23` |  
| `/jailstatus` | Shows jailed players & times | `/jailstatus` |  

---

## **🛠️ Troubleshooting**  

### **Players Not Being Jailed?**  
✅ Ensure `EasyAdmin-Ox` is installed and running  
✅ Check if the player ID is correct (`/jailstatus` to verify)  
✅ Verify staff permissions in `Config.AllowedStaff`  

### **Players Escaping Jail?**  
✅ Ensure `Config.PreventEscape = true`  
✅ Check if another script is overriding teleportation  

### **Console Errors?**  
✅ Verify dependencies (`ox_lib`, `EasyAdmin-Ox`)  
✅ Restart with `refresh` and `ensure OGDev-Jail-System`  

---

## **📢 Support & Contributions**  
For bug reports or feature requests, open an issue on GitHub!  
