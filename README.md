# WordPress Multi-Outlet E-Commerce — Custom Plugin Suite (Architecture Overview)

This repository provides a high-level architectural overview of a custom plugin system developed to extend WooCommerce for a multi-outlet retail business.  
The production codebase is proprietary; this documentation highlights the logic, workflows, and technical contributions implemented.

---

## 🛒 Project Overview

The business operates multiple physical outlets. Standard WooCommerce does not support:

- Per-outlet inventory
- Location-based outlet assignment
- Geofencing
- Single-outlet cart enforcement
- Per-outlet stock restrictions
- Delivery/pickup timeslot flows

To solve this, a set of custom WordPress plugins were developed.

---

## 🚀 Key Features

### 🏪 Multi-Outlet Architecture
- Each outlet has independent inventory.
- Product visibility is filtered based on outlet selection.
- Admins manage outlet-level configurations.

### 📍 Automatic Nearest-Outlet Selection
- Geo-location captured via browser.
- Distance calculated to all outlets.
- Nearest outlet automatically assigned.
- Manual override supported.

### 🛑 Geofencing + Polygon Validation
- Delivery region mapped using polygon/waypoint boundaries.
- If user selects a location outside allowed region →  
  **“Delivery not supported in this area.”**

### 🔒 Single-Outlet Cart Restriction
- Cart items must belong to one outlet.
- Prevents mixed-outlet checkout conflicts.

### 🛍️ Outlet-Level Stock Control
- Only products in stock at selected outlet are shown.
- Out-of-stock items marked unavailable for that outlet.

### 🚚 Delivery & Pickup Flows
- Customer selects mode:
  - Delivery → timeslot + address validation  
  - Pickup → timeslot + outlet confirmation
- User notes supported (“Leave at door”, etc.)

### ⏱️ Timeslot Management
- Admin defines delivery/pickup intervals.
- Validations applied before checkout.

### 🔑 Login-Before-Cart Rule
- Users must log in before adding products to cart.
- Prevents anonymous mixed-outlet carts.

---

## 💻 Technical Components

- Custom WooCommerce actions & filters
- Custom REST endpoints (selected flows)
- Session management for outlet selection
- Custom database tables for outlet mapping
- Polygon-based geofencing logic
- Stock synchronization at outlet level

---

## 👨‍💻 My Responsibilities

- Designed plugin architecture
- Implemented geolocation + nearest outlet logic
- Added geofencing polygon validation
- Developed checkout restrictions (single-outlet rule)
- Customized stock visibility per outlet
- Built delivery/pickup workflow logic
- Integrated user session rules (login-before-cart)

---

## ⚠️ Disclaimer
This repository contains **documentation only**.  
The actual plugin source code is not published due to organizational confidentiality.
