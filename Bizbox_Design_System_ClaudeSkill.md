# BizBox Design System v2

**Product:** BizBox Profiling — Health Information Platform (HIH)  
**Network:** Quezon Provincial Hospital Network (QPHN) · Bondoc Peninsula  
**Stack:** React 18 · MUI v9 · Poppins · Vite  
**Version:** DS v2  

---

## Table of Contents

1. [Design Tokens](#1-design-tokens)
2. [Typography](#2-typography)
3. [Navigation](#3-navigation)
4. [Status Pills](#4-status-pills)
5. [Iconography](#5-iconography)
6. [Table](#6-table)
7. [Forms](#7-forms)
8. [Buttons](#8-buttons)
9. [Components](#9-components)
10. [Throbbers / Loading](#10-throbbers--loading)

---

## 1. Design Tokens

### Color — Light Mode

| Token | Value | Usage |
|---|---|---|
| `--navy` | `#123257` | Primary brand, headings, interactive |
| `--navy-mid` | `#365F91` | Hover states, secondary navy |
| `--coral` | `#FF5F47` | CTA accent, highlights, today indicator |
| `--coral-hover` | `#DE3218` | Coral hover state |
| `--bg-page` | `#F2F5FB` | Page background |
| `--bg-card` | `#FFFFFF` | Card / surface background |
| `--bg-subtle` | `#F8FAFB` | Subtle fills, zebra rows |
| `--text-heading` | `#123257` | Page titles, card headings |
| `--text-body` | `#6D87AA` | Body copy, labels, secondary text |
| `--text-strong` | `#374151` | Emphasized body text |
| `--border` | `#E0E8EF` | Default dividers, card outlines |
| `--border-strong` | `#8A9FBB` | Input borders, active outlines |
| `--success` | `#0E9F6E` | Success states |
| `--danger` | `#F05252` | Errors, destructive actions |
| `--warning` | `#FACA15` | Warnings |
| `--disabled` | `#A1A1A1` | Disabled controls |
| `--placeholder` | `#6D87AA` | Input placeholder text |

### Color — Dark Mode Overrides

| Token | Value |
|---|---|
| `--bg-page` | `#0D1E2E` |
| `--bg-card` | `#162E4A` |
| `--bg-subtle` | `#122540` |
| `--text-heading` | `#E8EFF7` |
| `--text-body` | `#8DB3D4` |
| `--text-strong` | `#C5D5E8` |
| `--border` | `#1F3D5C` |
| `--border-strong` | `#2A4E72` |
| `--disabled` | `#3A6080` |
| `--placeholder` | `#3A6080` |
| `--coral` | `#FF7A65` |
| `--coral-hover` | `#C94030` |

### Color Scheme Usage Rules

**Do use:**
- `#FF5F47` / `#E65100` — Deep Orange for CTA & Accent
- `#123257` / `#1565C0` — Navy for Primary Actions & Nav
- `#00897B` / `#2E7D32` — Teal/Green for Success & Confirmations
- White for card surfaces
- Dark navy for high-contrast text

**Don't use:**
- `#C62828` — Bright red (reserved for critical errors only)
- `#4527A0` / `#7B1FA2` — Deep purple (not a brand color)
- `#00838F` / `#0066CC` — Teal-cyan or generic blue (off-brand)

### Secondary Color Suggestions

For charts, tags, or categorical data that needs variety beyond the primary palette:

| Name | Hex |
|---|---|
| Coral (primary accent) | `#FF5F47` |
| Dusty Blue | `#3D7EAA` |
| Dusty Teal | `#2E8B80` |
| Dusty Purple | `#8B4FA8` |
| Dusty Peach | `#D4784A` |
| Steel Blue | `#3A6EA8` |
| Sage Green | `#4A8C50` |
| Dusty Rose | `#C0514A` |
| Dusty Indigo | `#6B52A8` |
| Dusty Cyan | `#3A8C8A` |

---

## 2. Typography

**Primary font:** Poppins (all UI text)  
**Display font:** Instrument Serif (decorative/editorial only)  
**Fallback:** Inter, system-ui, sans-serif

### Type Scale

| Role | Size | Weight | Usage |
|---|---|---|---|
| Page Title | 30px | 700 | `<h1>` Patient Profile, Dashboard title |
| Section Heading | 24px | 600 | `<h2>` CVD/NCD Assessment, card titles |
| Sub-heading | 18px | 600 | `<h3>` Vitals Overview, panel headers |
| Body Strong | 16px | 500 | Patient Records, table cell primary text |
| Section Label | 12px | 600 | `MATERNAL HEALTH` — uppercase nav categories |
| Helper / Error | 12px | 500 | `This field is required.` — form helper text |

### Rules

- All text uses `font-family: 'Poppins', sans-serif`
- Section category labels are always `text-transform: uppercase` + `letter-spacing: 0.06em`
- Error text is always `color: var(--danger)` at 12px / 500
- Never mix Instrument Serif with UI controls — display/decorative use only

---

## 3. Navigation

### Sidebar Anatomy

```
┌─────────────────────────────┐
│  [Logo]  BizBox Profiling   │  ← 64px logo area
│          QPHN · Bondoc      │
├─────────────────────────────┤
│  MAIN                       │  ← 12px / 600 category label
│  ▣  Dashboard          ●   │  ← Active item (coral dot)
│  👥 Patient Records        │
│  📅 Appointments            │
│  💉 Vitals & EMR            │
│  📊 FHSIS Reports           │
│  🔬 MDA Tracking            │
│  🤰 Maternal Health         │
└─────────────────────────────┘
```

### Navigation Items

| Label | Icon type |
|---|---|
| Dashboard | Grid/overview |
| Patient Records | People group |
| Appointments | Calendar |
| Vitals & EMR | Medical cross |
| FHSIS Reports | Chart bar |
| MDA Tracking | Microscope |
| Maternal Health | Pregnant person |

### Sidebar Specs

| Property | Value |
|---|---|
| Width — expanded | 240px |
| Width — collapsed | 64px |
| Background | `--navy` (#123257) |
| Item height | 44px |
| Active indicator | 4px coral left border + coral dot |
| Icon size | 20×20px |
| Label font | 14px / 500 / white |
| Category label | 12px / 600 / rgba(255,255,255,0.4) |
| Collapse trigger | Chevron button at bottom |

### States

- **Default:** icon + label, white at 70% opacity
- **Hover:** white at 100% opacity + subtle bg highlight
- **Active:** white 100% + coral 4px left accent + active dot
- **Collapsed:** icon only, tooltip on hover

---

## 4. Status Pills

### Anatomy

```
● Label
```

- Dot: 6×6px circle  
- Padding: 4px 10px  
- Font: 12px / 500  
- Border-radius: 999px (full pill)  
- Dot hidden in WCAG AAA mode (color not used as sole indicator)

### Pill Color System

Pills use semantic color families consistently across all groups:

| Semantic meaning | Background | Text | Dot |
|---|---|---|---|
| **Active / Success / Confirmed** | `#DEF7EC` | `#03543F` | `#03543F` |
| **Scheduled / Completed / Sent** | `#EBF5FF` | `#1E429F` | `#1E429F` |
| **Warning / Rescheduled / Pending** | `#FDF6B2` | `#723B13` | `#723B13` |
| **Danger / No-show / Abnormal** | `#FDE8E8` | `#9B1C1C` | `#9B1C1C` |
| **Neutral / Inactive / Cancelled** | `#F3F4F6` | `#6B7280` | `#6B7280` |
| **Purple / Special / Telemedicine** | `#EDE9FE` | `#4C1D95` | `#4C1D95` |
| **Critical / Emergency (inverted)** | `#9B1C1C` | `#FFFFFF` | `#FFFFFF` |
| **Priority Patient (inverted)** | `#5B21B6` | `#FFFFFF` | `#FFFFFF` |
| **Pending (outlined)** | `#F0F3F7` | `#6D87AA` | `#9CA3AF` |

### Pill Groups & Statuses

**Patient Record**
Active · New Patient · Transferred · Inactive · Deceased · Archived · Priority Patient

**Appointment**
Scheduled · Confirmed · Arrived · Telemedicine · Walk-in · Rescheduled · No-show · Cancelled · Emergency

**Triage / Consultation Priority**
Urgent · Priority · Routine · Non-urgent

**Clinical / Lab Result**
Observation · Discharged · Normal · Borderline · Abnormal · Critical Value · Inconclusive · For Repeat · Reviewed · Pending

**Prescription / Medication**
Active · On Hold · Refill Due · Completed · Discontinued · Controlled Drug · Expired

**Maternal Health**
Low Risk · Moderate Risk · High Risk · Postpartum · Delivered · Referred Out · Lost to Follow-up

**MDA / Health Program**
Treated · Completed · Under Evaluation · Referred · Refused · Missed · Ineligible

**Referral / Care Coordination**
Sent · Accepted · Received · For Review · In Transit · Declined · Closed

**FHSIS Report Lifecycle**
Draft · Under Review · Final · Exported · Amended · Finalized · Overdue

**Sync / Data Status**
Synced · Processing · Conflict · Pending Sync · Sync Failed · Offline

**User / Access Control**
Super Admin · Admin · Auditor · Staff · Viewer · Pending Access · Suspended

---

## 5. Iconography

All icons are custom SVG path-based, sized at 24×24px (display) and 20×20px (nav/inline). Color inherits from `currentColor` or is set to `var(--navy)`.

### Icon Categories

| Category | Color |
|---|---|
| Body & Anatomy | `#C2185B` |
| Vitals & Measurements | `#FF5F47` (coral) |
| Conditions & Diagnosis | `#9B1C1C` |
| Clinical Procedures | `#0E9F6E` |
| Pharmacy & Medication | `#4C1D95` |
| Maternal & Child Health | `#831843` |
| MDA & Epidemiology | `#6D28D9` |
| Facility & Equipment | `#123257` (navy) |

### Sizes

| Context | Size |
|---|---|
| Navigation sidebar | 20×20px |
| Section / page header | 24×24px |
| Inline body text | 16×16px |
| Button icon | 18×18px |
| Badge / pill | 12×12px |

### Icon Library (76 icons)

Install: `npm install @mui/icons-material`  
Import pattern: `import BloodtypeIcon from '@mui/icons-material/Bloodtype'`

> Icons marked `*custom*` have no direct MUI equivalent — use `SvgIcon` wrapper with a custom path.

#### Body & Anatomy — `#C2185B`

| Label | MUI Icon | Import |
|---|---|---|
| blood drop | `Bloodtype` | `@mui/icons-material/Bloodtype` |
| blood type | `Bloodtype` | `@mui/icons-material/Bloodtype` |
| heart | `Favorite` | `@mui/icons-material/Favorite` |
| lungs | `AirOutlined` | `@mui/icons-material/AirOutlined` |
| brain | `PsychologyOutlined` | `@mui/icons-material/PsychologyOutlined` |
| kidney | `FilterAlt` ¹ | `@mui/icons-material/FilterAlt` |
| liver | `*custom*` | SvgIcon wrapper |
| stomach | `*custom*` | SvgIcon wrapper |
| bone | `*custom*` | SvgIcon wrapper |
| eye | `Visibility` | `@mui/icons-material/Visibility` |
| ear | `HearingOutlined` | `@mui/icons-material/HearingOutlined` |
| spine | `AccessibilityNew` ¹ | `@mui/icons-material/AccessibilityNew` |
| skin lesion | `*custom*` | SvgIcon wrapper |
| wound | `HealingOutlined` | `@mui/icons-material/HealingOutlined` |
| cell | `BiotechOutlined` | `@mui/icons-material/BiotechOutlined` |

> ¹ Closest semantic match — not exact.

#### Vitals & Measurements — `#FF5F47`

| Label | MUI Icon | Import |
|---|---|---|
| heart rate | `MonitorHeart` | `@mui/icons-material/MonitorHeart` |
| blood pressure | `*custom*` | SvgIcon wrapper |
| temperature | `ThermostatOutlined` | `@mui/icons-material/ThermostatOutlined` |
| weight | `FitnessCenterOutlined` | `@mui/icons-material/FitnessCenterOutlined` |
| height | `HeightOutlined` | `@mui/icons-material/HeightOutlined` |
| bmi | `AccessibilityOutlined` | `@mui/icons-material/AccessibilityOutlined` |
| o2 sat | `AirOutlined` | `@mui/icons-material/AirOutlined` |
| respiratory | `AirOutlined` | `@mui/icons-material/AirOutlined` |
| glucose | `WaterDropOutlined` | `@mui/icons-material/WaterDropOutlined` |
| waist circ | `*custom*` | SvgIcon wrapper |
| head circum | `*custom*` | SvgIcon wrapper |

#### Conditions & Diagnosis — `#9B1C1C`

| Label | MUI Icon | Import |
|---|---|---|
| hypertension | `MonitorHeart` | `@mui/icons-material/MonitorHeart` |
| diabetes | `WaterDropOutlined` | `@mui/icons-material/WaterDropOutlined` |
| cvd risk | `FavoriteOutlined` | `@mui/icons-material/FavoriteOutlined` |
| smoking | `SmokingRoomsOutlined` | `@mui/icons-material/SmokingRoomsOutlined` |
| malnutrition | `NoMealsOutlined` | `@mui/icons-material/NoMealsOutlined` |
| allergy | `WarningAmberOutlined` | `@mui/icons-material/WarningAmberOutlined` |
| asthma | `AirOutlined` | `@mui/icons-material/AirOutlined` |
| infection | `CoronavirusOutlined` | `@mui/icons-material/CoronavirusOutlined` |

#### Clinical Procedures — `#0E9F6E`

| Label | MUI Icon | Import |
|---|---|---|
| consultation | `MedicalServicesOutlined` | `@mui/icons-material/MedicalServicesOutlined` |
| surgery | `HealingOutlined` | `@mui/icons-material/HealingOutlined` |
| injection | `VaccinesOutlined` | `@mui/icons-material/VaccinesOutlined` |
| lab test | `BiotechOutlined` | `@mui/icons-material/BiotechOutlined` |
| imaging | `RadioOutlined` | `@mui/icons-material/RadioOutlined` |
| dressing | `HealingOutlined` | `@mui/icons-material/HealingOutlined` |
| nebulization | `AirOutlined` | `@mui/icons-material/AirOutlined` |
| phlebotomy | `Bloodtype` | `@mui/icons-material/Bloodtype` |
| referral out | `SendOutlined` | `@mui/icons-material/SendOutlined` |
| discharge | `ExitToAppOutlined` | `@mui/icons-material/ExitToAppOutlined` |

#### Pharmacy & Medication — `#4C1D95`

| Label | MUI Icon | Import |
|---|---|---|
| tablet | `MedicationOutlined` | `@mui/icons-material/MedicationOutlined` |
| prescription | `DescriptionOutlined` | `@mui/icons-material/DescriptionOutlined` |
| pharmacy | `LocalPharmacyOutlined` | `@mui/icons-material/LocalPharmacyOutlined` |
| iron tablet | `MedicationOutlined` | `@mui/icons-material/MedicationOutlined` |
| syrup | `OpacityOutlined` | `@mui/icons-material/OpacityOutlined` |
| iv drip | `WaterDropOutlined` | `@mui/icons-material/WaterDropOutlined` |
| controlled | `LockOutlined` | `@mui/icons-material/LockOutlined` |
| supplement | `MedicationLiquidOutlined` | `@mui/icons-material/MedicationLiquidOutlined` |

#### Maternal & Child Health — `#831843`

| Label | MUI Icon | Import |
|---|---|---|
| prenatal | `PregnantWomanOutlined` | `@mui/icons-material/PregnantWomanOutlined` |
| delivery | `ChildCareOutlined` | `@mui/icons-material/ChildCareOutlined` |
| breastfeed | `BreastfeedingOutlined` | `@mui/icons-material/BreastfeedingOutlined` |
| immunization | `VaccinesOutlined` | `@mui/icons-material/VaccinesOutlined` |
| family plan | `FamilyRestroomOutlined` | `@mui/icons-material/FamilyRestroomOutlined` |
| growth chart | `ShowChartOutlined` | `@mui/icons-material/ShowChartOutlined` |
| newborn | `BabyChangingStationOutlined` | `@mui/icons-material/BabyChangingStationOutlined` |
| postnatal | `EscalatorWarningOutlined` | `@mui/icons-material/EscalatorWarningOutlined` |

#### MDA & Epidemiology — `#6D28D9`

| Label | MUI Icon | Import |
|---|---|---|
| filariasis | `BugReportOutlined` | `@mui/icons-material/BugReportOutlined` |
| vector control | `PestControlOutlined` | `@mui/icons-material/PestControlOutlined` |
| mass drug | `MedicationOutlined` | `@mui/icons-material/MedicationOutlined` |
| surveillance | `MonitorOutlined` | `@mui/icons-material/MonitorOutlined` |
| coverage map | `MapOutlined` | `@mui/icons-material/MapOutlined` |
| outbreak | `CoronavirusOutlined` | `@mui/icons-material/CoronavirusOutlined` |
| community | `GroupsOutlined` | `@mui/icons-material/GroupsOutlined` |
| health worker | `BadgeOutlined` | `@mui/icons-material/BadgeOutlined` |

#### Facility & Equipment — `#123257`

| Label | MUI Icon | Import |
|---|---|---|
| hospital | `LocalHospitalOutlined` | `@mui/icons-material/LocalHospitalOutlined` |
| rhu | `MapsHomeWorkOutlined` | `@mui/icons-material/MapsHomeWorkOutlined` |
| ambulance | `AirportShuttleOutlined` | `@mui/icons-material/AirportShuttleOutlined` |
| operating room | `MedicalServicesOutlined` | `@mui/icons-material/MedicalServicesOutlined` |
| laboratory | `ScienceOutlined` | `@mui/icons-material/ScienceOutlined` |
| ward | `BedroomParentOutlined` | `@mui/icons-material/BedroomParentOutlined` |
| waiting area | `EventSeatOutlined` | `@mui/icons-material/EventSeatOutlined` |
| records room | `FolderOpenOutlined` | `@mui/icons-material/FolderOpenOutlined` |

### Rules

- Always use `fill="currentColor"` — never hardcode hex in SVG `fill`
- Set color on the parent container, not the SVG element directly
- Nutrition icon uses a rice bowl SVG (not a generic nutrition icon)
- Facility icon uses a hospital building SVG

---

## 6. Table

### Table Specs

| Property | Value |
|---|---|
| Header font | 11px / 700 / uppercase / letter-spacing 0.06em |
| Header color | `--text-body` |
| Header background | `--bg-subtle` |
| Row height | 48px |
| Cell font | 14px / 400 / `--text-heading` |
| Zebra row | every other row `--bg-subtle` |
| Border | 1px `--border` horizontal only |
| Radius | 8px on outer container |

### Column Types

- **Patient name** — bold 14px / 600, with avatar or initials chip
- **Status** — always a Status Pill (see §4)
- **Date / time** — 13px / 400 monospace-aligned
- **Actions** — icon buttons only, right-aligned

---

## 7. Forms

### 7.1 Text Field

Standard BizBox input with floating label.

| Property | Value |
|---|---|
| Height | 44px |
| Border-radius | 16px |
| Border default | 1.5px `--border-strong` |
| Border focus | 1.5px `--navy` |
| Border error | 1.5px `--danger` |
| Label (floating up) | 12px / 500 `--navy` |
| Input font | 16px (prevents iOS zoom) |
| Background | `--bg-card` |

**States:** Default · Filled · Focused · Error · Disabled · Optional

Error helper text: 12px / 500 / `--danger` with warning icon (SVG inline, 13×13px).

### 7.2 Phone Number

Identical to Text Field with a `+63` prefix chip prepended inside the input.

| Property | Value |
|---|---|
| Prefix chip | `+63` · 14px / 600 · navy background |
| Input type | `tel` |
| Placeholder | `Mobile Number` |

### 7.3 Dropdown

Native `<select>` styled to match BizBox inputs.

| Property | Value |
|---|---|
| Height | 44px |
| Border-radius | 16px |
| Chevron | Custom SVG, right-aligned |
| Font | 16px Poppins |

### 7.4 Facility Selector Dropdown

Custom dropdown for selecting a healthcare facility. Not a native `<select>`.

| Property | Value |
|---|---|
| Trigger height | 44px |
| Width | 250px default, up to 500px expanded |
| Border-radius | 16px (collapsed) · 16px 16px 0 0 (open) |
| Avatar | 32px circular, navy background, white facility icon |
| Facility name | 16px / 600 |
| Label | 14px / 400 `--text-body` |
| Max width (expanded) | 500px |

**States:** Collapsed (default) · Expanded (open, shows list)

```html
<!-- Usage -->
<div class="fac-wrap" id="fac-dd">
  <div class="fac-trigger" onclick="toggleFacDD()" id="fac-trigger">
    <div class="fac-avatar-placeholder"><!-- facility SVG icon --></div>
    <div class="fac-text">
      <span class="fac-label">Facility</span>
      <span class="fac-name">Bondoc Peninsula RHU</span>
    </div>
    <span class="fac-chevron" id="fac-chevron"><!-- chevron SVG --></span>
  </div>
  <div class="fac-panel" id="fac-panel" style="display:none">
    <div class="fac-opt" onclick="selectFac(this,'Bondoc Peninsula RHU')">
      <div class="fac-opt-text">
        <span class="fac-opt-label">Facility</span>
        <span class="fac-opt-name">Bondoc Peninsula RHU</span>
      </div>
    </div>
    <!-- more options -->
  </div>
</div>
```

### 7.5 Search Box

| Property | Value |
|---|---|
| Height | 52px |
| Border-radius | 999px (full pill) |
| Background | `--bg-subtle` (light gray fill, no border) |
| Input font | 15px Poppins · `--placeholder` color |
| Search button | 40×40px circle · navy fill · white icon · `right: 6px` inset |
| Button hover | `--navy-mid` |
| Icon | MUI `Search` · 20×20px · `fill="white"` |
| Icon import | `@mui/icons-material/Search` |
| Focused state | `box-shadow: 0 0 0 2px var(--navy)` on wrap |
| Error state | `box-shadow: 0 0 0 2px var(--danger)` + danger button |
| Disabled | `opacity: 0.55` on wrap |
| Placeholder | `Search patients...` |

### 7.6 Labeled Input (Floating Label variant)

Floating label that animates up on focus/fill. Used in modals and dense forms.

| Property | Value |
|---|---|
| Height | 44px |
| Border-radius | 16px |
| Label resting | 16px / inside input vertically centered |
| Label active | 12px / lifted above input top edge |
| Border focus | 1.5px `--navy` |

### 7.7 Date Picker & Date-Time Picker

MUI X v9-style date and datetime pickers.

#### Date Picker

| Property | Value |
|---|---|
| Field height | 56px (MUI standard) |
| Border-radius | 4px (Material Design) |
| Paper elevation | 8dp box-shadow |
| Calendar width | 320px |
| Day cell | 36×36px circular |
| Today indicator | Outlined circle, navy border |
| Selected | Filled navy circle |
| Action buttons | `CANCEL` · `OK` — text buttons, uppercase, navy |

```html
<!-- Usage -->
<div class="dp-wrap" id="dpA">
  <div class="dp-field">
    <div class="dp-field-inner" id="dpA-tr" onclick="DP.toggle('dpA','date')">
      <span class="dp-field-label">Date</span>
      <span class="dp-field-text" id="dpA-val">MM / DD / YYYY</span>
      <span class="dp-field-ico"><!-- calendar icon --></span>
    </div>
  </div>
  <div class="dp-paper" id="dpA-panel" style="display:none">
    <!-- calendar header, grid, actions -->
  </div>
</div>
```

#### Date & Time Picker

Extends the Date Picker with a tab system.

| Property | Value |
|---|---|
| Field width | min 260px |
| Tabs | Date · Time (icon + label) |
| Time view | 3-column scrollable clock: Hour · Min · AM/PM |
| Hour column | 01–12 (padded) |
| Minute column | 00, 05, 10 … 55 (5-min steps) |
| AM/PM column | AM · PM |
| Selected time item | Navy pill (border-radius 18px) |
| Scroll behavior | Auto-scrolls selected item into center on open |

**Behaviour:**
- Clicking OK without selecting a date first → switches back to Date tab and flashes month title coral
- Clicking a day selects it; clicking OK on Date tab with a date → confirms
- Clicking OK on Time tab with date selected → confirms full datetime

---

## 8. Buttons

### 8.1 Primary & ADD Buttons

| Property | Value |
|---|---|
| Height | 44px |
| Border-radius | 16px |
| Background | `--navy` |
| Text color | `#FFFFFF` |
| Font | 14px / 600 Poppins |
| Hover | `--navy-mid` |
| Padding | 0 24px |

**ADD Button** — special variant:
- 44×44px square with `+` icon
- Navy background, white icon
- Used as a floating or inline action trigger

### 8.2 Modal Buttons

Used inside dialogs for confirm/cancel actions.

| Variant | Style |
|---|---|
| Confirm | Navy fill, white text, 16px radius |
| Cancel | Transparent, navy text, navy border |
| Destructive | `--danger` fill, white text |

### 8.3 Icon Buttons

| Property | Value |
|---|---|
| Size | 40×40px |
| Border-radius | 8px |
| Icon size | 20×20px |
| Background | Transparent (hover: `--bg-subtle`) |
| Active | Navy background, white icon |

### 8.4 Segmented Control

Pill-shaped toggle group for switching views.

| Property | Value |
|---|---|
| Height | 36px |
| Border-radius | 999px (pill) |
| Track background | `--bg-subtle` |
| Selected segment | Navy fill, white text |
| Font | 13px / 500 |
| Transition | 150ms ease |

---

## 9. Components

### 9.1 Stepper

Numbered step indicator used in multi-step flows (e.g. patient registration).

- Step circles: 28px diameter
- Active: navy fill, white number
- Complete: coral fill + checkmark icon
- Any completed step is navigable (clickable)
- Connector line: 1px `--border`, turns navy when step complete

### 9.2 Notification Bell

| Property | Value |
|---|---|
| Container | 24×24px |
| Icon | Navy, 20×20px |
| Badge | Coral filled circle, white number, 16px min-width |
| Badge position | Top-right, -4px offset |
| Badge font | 10px / 700 |

### 9.3 Snackbar / Toast

| Property | Value |
|---|---|
| Duration | 3–5 seconds |
| Font | 16px Poppins |
| Animation | Slide down from top |
| Position | Top-center |
| Variants | Success (green) · Error (red) · Warning (yellow) · Info (navy) |
| Border-radius | 8px |
| Min width | 300px |

### 9.4 Body Header

| Property | Value |
|---|---|
| Height | 64px |
| Background | Navy with coral 4px bottom accent stripe |
| Title | 18px / 600 white |
| Subtitle | 13px / 400 rgba(255,255,255,0.7) |
| Back button | Left arrow icon, white |
| Actions area | Right-aligned icon buttons |

### 9.5 Upload Container

| Property | Value |
|---|---|
| Border | 2px dashed `--border-strong` |
| Border-radius | 12px |
| Background | `--bg-subtle` |
| Drag active | Navy dashed border + subtle navy tint |
| Icon | Upload cloud, navy, 32px |
| Helper text | 13px `--text-body` |
| File constraints | Displayed below drop zone |

---

## 10. Throbbers / Loading

Loading animation components for async states.

### Variants

| Name | Description |
|---|---|
| Spinner | Circular rotating arc, 24px, `--navy` |
| Pulse | Scaling dot, 12px, `--coral` |
| Skeleton | Gray shimmer bars matching content shape |
| Blob | Organic morphing shape, full-screen overlay |
| Dots | Three bouncing dots, inline use |

### Usage Rules

- **Spinner** — button loading states, small async actions
- **Skeleton** — table rows, card content loading (prefer over spinners for layout-preserving UX)
- **Blob** — full-page initial load only
- **Dots** — inline text or chat-style loading indicators
- Always pair loading states with `aria-busy="true"` and a visually hidden status message

---

## Appendix: CSS Custom Property Reference

```css
:root {
  /* Brand */
  --navy:         #123257;
  --navy-mid:     #365F91;
  --coral:        #FF5F47;
  --coral-hover:  #DE3218;

  /* Backgrounds */
  --bg-page:      #F2F5FB;
  --bg-card:      #FFFFFF;
  --bg-subtle:    #F8FAFB;

  /* Text */
  --text-heading: #123257;
  --text-body:    #6D87AA;
  --text-strong:  #374151;

  /* Borders */
  --border:       #E0E8EF;
  --border-strong:#8A9FBB;

  /* Semantic */
  --success:      #0E9F6E;
  --danger:       #F05252;
  --warning:      #FACA15;
  --disabled:     #A1A1A1;
  --placeholder:  #6D87AA;
}
```

---

*BizBox Design System v2 · Generated from DS v2 interactive reference · QPHN Bondoc Peninsula*
