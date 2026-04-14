# Library & SDK Version Audit Specification

## Overview
This document tracks all library and SDK versions used in the project, identifies which ones need upgrading, and documents the upgrade process.

---

## Current Library Versions

| Library | Current Version | Latest Version | Status | Priority |
|---------|------------------|----------------|--------|----------|
| jQuery | 3.7.1 | 4.0.0 | ⚠️ Minor update available | Medium |
| jQuery Remodal | 1.1.1 | 1.1.1 | ✅ Up to date | - |
| jQuery Swipebox | 1.3.0.2 | N/A | ⚠️ Unmaintained | Low |
| FontAwesome | 4.3.0 | 6.x | ✅ Upgrade available | High |
| skel | 3.0.1 | N/A | ⚠️ Unmaintained | Low |
| please-wait | 0.0.5 | 0.0.5 | ✅ Up to date | - |

---

## Upgradeable Libraries

### 1. FontAwesome (High Priority)

**Current**: 4.3.0 → **Latest**: 6.x

| Aspect | Details |
|--------|---------|
| Files | `fonts/*`, `css/font-awesome.min.css` |
| Breaking Changes | Yes - class names changed (e.g., `fa-fa` → `fa-solid fa-earth-americas`) |
| Impact | High - requires HTML changes for icons |

**Action Items**:
- [ ] Download FontAwesome 6.x
- [ ] Replace font files in `fonts/`
- [ ] Replace CSS in `css/font-awesome.min.css`
- [ ] Update icon class names in HTML files
- [ ] Test all icons render correctly

---

### 2. jQuery (Medium Priority)

**Current**: 3.7.1 → **Latest**: 4.0.0

| Aspect | Details |
|--------|---------|
| Files | `js/jquery.min.js` |
| Breaking Changes | Some deprecated APIs removed |
| Impact | Medium - may break older jQuery plugins |

**Action Items**:
- [ ] Download jQuery 4.0.0
- [ ] Replace `js/jquery.min.js`
- [ ] Test all jQuery-dependent plugins
- [ ] Verify no console errors

---

### 3. jQuery Swipebox (Low Priority)

**Current**: 1.3.0.2 → **Latest**: N/A

| Aspect | Details |
|--------|---------|
| Files | `js/jquery.swipebox.js` |
| Status | Unmaintained - no recent releases |
| Recommendation | Consider alternative or custom solution |

**Action Items**:
- [ ] Evaluate alternative lightbox libraries
- [ ] Or maintain current version (still functional)

---

### 4. skel (Low Priority)

**Current**: 3.0.1 → **Latest**: N/A

| Aspect | Details |
|--------|---------|
| Files | `js/skel.min.js` |
| Status | Unmaintained |
| Recommendation | Keep current version |

---

## Progress Tracking Table

| Library | Status | Completed Date |
|---------|--------|----------------|
| jQuery | ⏳ Pending | - |
| jQuery Remodal | ✅ N/A | - |
| jQuery Swipebox | ⏸️ Not needed | - |
| FontAwesome | ⏳ Pending | - |
| skel | ⏸️ Not needed | - |
| please-wait | ✅ N/A | - |

---

## References
- [jQuery Releases](https://github.com/jquery/jquery/releases)
- [FontAwesome 6 Upgrade Guide](https://fontawesome.com/docs/web/setup/upgrade/whats-changed)
- [jQuery Migrate Plugin](https://github.com/jquery/jquery-migrate/) - helps with jQuery upgrades
