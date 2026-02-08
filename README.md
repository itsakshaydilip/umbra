# Umbra - Maya Model Scene Cleaner & Checker

**Version:** 2.0  
**Last Updated:** January 2026  
**Compatible with:** Autodesk Maya (All versions with PySide2 support)

> Comprehensive model scene cleanup and validation tool with one-click batch operations and character model checking utilities.

---

## Overview

Umbra is a production-focused Maya tool that combines scene cleanup operations and character model validation into a single, streamlined interface. Features include automated node cleanup, geometry organization, pivot management, and character model checks with custom button architecture for easy workflow integration.

---

## Features

- **Model Scene Cleaner** - 6 cleanup operations for production-ready models
- **Character Model Checks** - Validation tools for character assets
- **Batch Operations** - "Run All" functionality for complete scene cleanup
- **Smart Cleanup** - Removes unwanted nodes, empty groups, and unused shaders
- **Pivot Management** - Center pivots and reset transforms
- **Viewport Optimization** - Bounding box display and frame all
- **Geometry Organization** - Auto-groups visible objects as 'GEO'
- **Custom Button System** - Reusable UmbraButton class for consistent UI
- **Dark Theme** - Professional dark color scheme

---

## Requirements

- **Software:** Autodesk Maya (any version with PySide2 support)
- **Python:** Maya's bundled Python environment
- **Dependencies:** PySide2 (included with Maya 2017+)

---

## Installation

### Quick Install

1. **Download** `ver02.Umbra.py` to your Maya scripts directory:
   ```
   Windows: C:\Users\<username>\Documents\maya\<version>\scripts\
   Mac:     ~/Library/Preferences/Autodesk/maya/<version>/scripts/
   Linux:   ~/maya/<version>/scripts/
   ```

2. **Restart Maya** or refresh scripts

### Verify Installation

Open Maya Script Editor (Python tab) and run:

```python
import ver02.Umbra as umbra
print("✓ Umbra loaded successfully!")
```

---

## Usage

### Launch the Tool

```python
import ver02.Umbra as umbra
# UI appears automatically on import in current implementation
# Or explicitly show with:
# umbra.Umbra().show()
```

### Basic Workflow

**Model Scene Cleaner:**
1. **Open** your Maya scene with model
2. **Launch** Umbra UI
3. **Run Individual Cleanups:**
   - Click specific cleanup buttons as needed
4. **Run All Cleanup:**
   - Click "Run All Cleanup" for complete scene processing

**Character Model Checks:**
1. **Select** character model group
2. **Run Individual Checks:**
   - Click specific validation buttons
3. **Run All Checks:**
   - Click "Run All Checks" for complete validation

---

## Key Components

### Model Scene Cleaner (6 Operations)

1. **Delete Unwanted Nodes**
   - Removes unnecessary scene nodes
   - Cleans up leftover construction nodes
   - Improves scene file size

2. **Delete Empty Groups**
   - Finds and removes empty group nodes
   - Cleans up hierarchy
   - Reduces scene clutter

3. **Center Pivot**
   - Centers pivot points on selected objects
   - Uses bounding box center
   - Improves transform manipulation

4. **Bounding Box + Frame**
   - Sets viewport to bounding box display mode
   - Frames all objects in view
   - Optimizes viewport performance

5. **Delete Unused Nodes**
   - Removes unused shading nodes
   - Cleans up materials and textures
   - Reduces file size

6. **Group Visible as 'GEO'**
   - Groups all visible geometry
   - Creates organized hierarchy
   - Names group as 'GEO' for consistency

**Run All Cleanup:**
- Executes all 6 cleanup operations sequentially
- One-click complete scene cleanup
- Safe batch processing

### Character Model Checks

- Validation tools for character assets
- Industry standard checks
- Quality assurance automation
- (Full check list in UI)

### Custom Button System

**UmbraButton Class Features:**
- Self-contained button with styling
- Auto-adds to grid layout at specified position
- Auto-connects click signals to functions
- Consistent dark theme styling
- Column spanning support

**Benefits:**
- Reduces boilerplate code (1 line vs 4 lines per button)
- Consistent appearance across UI
- Easy to maintain and extend
- Modular button architecture

---

## Troubleshooting

### UI doesn't appear
- Verify PySide2 is available in Maya version
- Check for conflicting window names
- Run from Script Editor to see error messages

### Cleanup operations fail
- Ensure scene has objects to process
- Check for locked or referenced nodes
- Verify no protected system nodes

### Empty groups not deleted
- Check groups aren't parented to locked objects
- Verify groups don't have attributes preventing deletion
- Ensure groups are truly empty (no hidden children)

### Viewport doesn't change
- Manually reset viewport if needed
- Check viewport settings aren't locked
- Verify display preferences allow changes

### Group 'GEO' already exists
- Tool will use existing group
- Or rename existing group before running
- Check Outliner for name conflicts

---

## Technical Details

- **Language:** Python 3.x (Maya 2017+ compatible)
- **UI Framework:** PySide2 (Qt-based)
- **Dependencies:** maya.cmds, maya.mel
- **Architecture:** Class-based with custom button subclass
- **Theme:** Dark (#1e1e1e background, #2b2b2b buttons)
- **Layout:** Grid-based with dynamic button placement

### Code Architecture

**Main Classes:**
- **Umbra** - Main dialog window
- **UmbraButton** - Custom QPushButton subclass

**Core Methods:**
- **delete_unwanted_nodes()** - Node cleanup logic
- **delete_empty_groups()** - Empty group removal
- **center_pivot()** - Pivot centering
- **set_viewport_bounding_box()** - Viewport configuration
- **delete_unused_nodes()** - Shading node cleanup
- **group_geo()** - Geometry grouping
- **run_all()** - Batch cleanup execution

### UI Layout

```
┌─────────────────────────────────┐
│  Model Scene Cleaner            │
├─────────────────┬───────────────┤
│ Delete Unwanted │ Delete Empty  │
│ Nodes           │ Groups        │
├─────────────────┼───────────────┤
│ Center Pivot    │ Bounding Box  │
│                 │ + Frame       │
├─────────────────┼───────────────┤
│ Delete Unused   │ Group Visible │
│ Nodes           │ as 'GEO'      │
├─────────────────┴───────────────┤
│      Run All Cleanup            │
└─────────────────────────────────┘
```

---

**Author:** Akshay Dilip Kumar - itsakshaydilip  
**License:** Apache License 2.0
