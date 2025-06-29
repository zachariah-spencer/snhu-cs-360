# SNHU CS-360: Inventory Tracker Android App

## Overview
This Android app provides busy small-business owners and warehouse staff with a simple, reliable way to track inventory in real time, even offline. It emphasizes ease of setup (get started in under a minute), secure access, and clear feedback when stock runs low.

## Requirements & Goals
- **Secure login & registration** to protect business data  
- **Real-time inventory grid** powered by local SQLite (Room) for fast, offline-first updates  
- **Low-stock alerts** via optional SMS or in-app notifications  
- **Clean, intuitive UI** compatible with Android 5.0+ (min SDK 21) through Android 8.0+ (target SDK 26)  
- **Flexible monetization**: free tier (up to 50 items + unobtrusive ads) and one-time Pro upgrade (unlimited items, no ads)  
- **Analytics & feedback**: basic in-app analytics and a “Send Feedback” form for post-launch iteration  

## User Needs
- **Warehouse managers** need glanceable dashboards and immediate restock alerts  
- **Small-business owners** want an affordable, low-overhead tool they can trust offline  
- **Clerks/employees** require fast add/remove actions and one-tap quantity updates during daily operations  

## Screens & Features

### Screens
- **Login & Registration**: secure sign-in with email/password  
- **Dashboard (Grid View)**: displays all items, quantities, and low-stock indicators  
- **Item Detail & Edit**: view history, adjust quantities, set thresholds  
- **Add New Item**: quick form with name, SKU, quantity, optional photo  
- **Alerts & Notifications**: in-app toast or SMS when stock hits zero  
- **Settings & Feedback**: permission toggles, Pro upgrade, and feedback form  

### UI Design Principles
- **Consistent grid layout** for rapid scanning of dozens of items  
- **High-contrast icons and color coding** to call out low-stock items  
- **Minimal taps**: primary actions (add, edit, restock) reachable in one or two touches  
- **Graceful degradation**: core features remain fully usable if SMS permission is denied  
- **Performance-first**: RecyclerView + DiffUtil ensures smooth scrolling on older devices  

## Implementation Approach
- **Architecture**: MVVM with Clean Architecture layers (UI → ViewModel → Repository → Room)  
- **Language & Frameworks**: Kotlin, Android Jetpack (LiveData, ViewModel, Room), Coroutines for async  
- **Dependency Injection**: Hilt to manage module lifecycles and support testing  
- **Modularity**: reusable UI components and well-defined data models for easy future feature additions  

## Testing Strategy
- **Unit Tests** (JUnit) for ViewModels and Repository logic  
- **UI Tests** (Espresso) for critical flows: login, add/edit item, low-stock alert  
- **Manual QA** across API 21–30 emulators and physical devices  
- **Results**: caught edge cases around permission denial, data migration bugs, and concurrency issues in the grid view  

## Challenges & Innovations
- **Optional SMS permission**: runtime-check pattern so users who decline SMS still enjoy full functionality  
- **Real-time UI updates**: leveraged Room’s Flow + LiveData with DiffUtil to animate only changed rows  
- **Offline-first reliability**: robust SQLite migrations and conflict-free update logic to prevent data loss  

## Key Component
The **real-time inventory grid** best demonstrates my skills:
- Tight integration of Room + LiveData for instant updates  
- High-performance RecyclerView setup with DiffUtil  
- Clean separation of concerns via MVVM, ensuring testability and maintainability  

