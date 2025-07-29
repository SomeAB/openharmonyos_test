# Changelog

### Overview
This document details the fixes required to cleanly build **OpenHarmony v5.1.x Release** version for the **QEMU x86_64 (with GUI)** target platform in a Docker environment.  
These changes are on top of the source code downloaded from the OpenHarmony website.

---

## List of Changes

#### 1. Compile Standard Whitelist Fix
- **Files changed**: `build/compile_standard_whitelist.json`  
- **Purpose**: Add missing subsystem component entries to compilation whitelist  
- **Extra Comment**: Required for successful compilation of QEMU x86_64 target. This fix might be changed in future, for now we are just suppressing the error by whitelisting things.

**Changes**:
```
- Added `device_qemu-x86_64-linux` to subsystem_components array
- Added `device_x86_64_virt` to subsystem_components array
- Added `product_qemu-x86_64-linux-min` to subsystem_components array
- Added `device/qemu/x86_64_virt/linux/ohos.build` to bundle_subsystem_error array
```

---

#### 2. Subsystem Components Whitelist Fix
- **Files changed**: `build/subsystem_components_whitelist.json`  
- **Purpose**: Register device and product configurations in build system  
- **Extra Comment**: Ensures all required device/product keys are present for build.

**Changes**:
```
- Added `device_qemu-x86_64-linux` → `device_qemu-x86_64-linux` mapping
- Added `product_qemu-x86_64-linux-min` → `product_qemu-x86_64-linux-min` mapping
- Added `device_x86_64_virt` → `device_x86_64_virt` mapping
```

---

#### 3. Core Configuration Updates
- **Files changed**: `vendor/ohemu/qemu_x86_64_linux_min/config.json`  
- **Purpose**: Modernize device naming and add essential runtime components  
- **Extra Comment**: Aligns with current OpenHarmony naming and enables async/runtime features.

**Changes**:
```
- Renamed subsystem: `device_x86_64_virt` → `device_qemu-x86_64-linux`
- Added `ylong_runtime` component to `commonlibrary` subsystem
- Created new `resourceschedule` subsystem with components:
  - `ffrt` (Fast Function Runtime)
  - `frame_aware_sched` (Frame-aware Scheduler)
```

---

#### 4A. Device Manager UI Dependency Removal
- **Files changed**: `foundation/distributedhardware/device_manager/BUILD.gn`  
- **Purpose**: Remove problematic UI dependency causing build failures  
- **Extra Comment**: Prevents build errors related to missing UI dependencies in headless/GUI builds.

**Changes**:
```
- Removed conditional block: `if (product_name != "qemu-arm-linux-min")`
- Eliminated `deps += [ "display/entry:DeviceManager_UI" ]` dependency
```

---

#### 4B. Template Modernization
- **Files changed**: `foundation/distributedhardware/device_manager/display/entry/BUILD.gn`  
- **Purpose**: Convert legacy HAP template to modern app template  
- **Extra Comment**: Ensures compatibility with modern OpenHarmony build templates.

**Changes**:
```
- Converted `ohos_hap("DeviceManager_UI")` → `ohos_app("DeviceManager_UI")`
- Added `app_type = "hap"` parameter
- Removed obsolete parameters: `publicity_file`, `certificate_profile`
- Removed deprecated signing block with `sign_hap_py_path`
```

---

#### 5. HiAppEvent Component Addition
- **Files changed**: `vendor/ohemu/qemu_x86_64_linux_min/config.json`  
- **Purpose**: Add accessibility interface support for application events  
- **Extra Comment**: Required for accessibility and event reporting in minimal builds.

**Changes**:
```
- Added `hiappevent` component to `hiviewdfx` subsystem
- Configured with empty features array for minimal deployment
```
