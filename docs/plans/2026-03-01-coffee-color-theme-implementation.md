# Coffee Color Theme Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Update KafuCafe theme colors to coffee-inspired palette with white backgrounds and brown accents.

**Architecture:** Modify Shopify theme color schemes in settings_data.json to apply coffee color palette across all scheme types.

**Tech Stack:** Shopify Liquid theme, JSON configuration

---

## Implementation Tasks

### Task 1: Update scheme-1 (Primary - White Background)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-1 color settings**

Replace scheme-1 settings with coffee palette:

```json
"scheme-1": {
  "settings": {
    "background": "#ffffff",
    "foreground_heading": "#2d2a26",
    "foreground": "#4a4540",
    "primary": "#6f4e37",
    "primary_hover": "#5d3e2c",
    "border": "#e8e2da",
    "shadow": "#2d2a26",
    "primary_button_background": "#6f4e37",
    "primary_button_text": "#ffffff",
    "primary_button_border": "#6f4e37",
    "primary_button_hover_background": "#5d3e2c",
    "primary_button_hover_text": "#ffffff",
    "primary_button_hover_border": "#5d3e2c",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#6f4e37",
    "secondary_button_border": "#6f4e37",
    "secondary_button_hover_background": "#faf7f2",
    "secondary_button_hover_text": "#5d3e2c",
    "secondary_button_hover_border": "#5d3e2c",
    "input_background": "#ffffff",
    "input_text_color": "#4a4540",
    "input_border_color": "#e8e2da",
    "input_hover_background": "#faf7f2",
    "variant_background_color": "#ffffff",
    "variant_text_color": "#4a4540",
    "variant_border_color": "#e8e2da",
    "variant_hover_background_color": "#f5ede4",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#d4ccc2",
    "selected_variant_background_color": "#6f4e37",
    "selected_variant_text_color": "#ffffff",
    "selected_variant_border_color": "#6f4e37",
    "selected_variant_hover_background_color": "#5d3e2c",
    "selected_variant_hover_text_color": "#ffffff",
    "selected_variant_hover_border_color": "#5d3e2c"
  }
}
```

**Step 2: Run theme check**

Run: `shopify theme check config/settings_data.json`

Expected: Valid JSON with no errors

**Step 3: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-1 to coffee color palette"
```

---

### Task 2: Update scheme-2 (Secondary - Cream Background)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-2 color settings**

Replace scheme-2 settings:

```json
"scheme-2": {
  "settings": {
    "background": "#faf7f2",
    "foreground_heading": "#2d2a26",
    "foreground": "#4a4540",
    "primary": "#6f4e37",
    "primary_hover": "#5d3e2c",
    "border": "#e8e2da",
    "shadow": "#2d2a26",
    "primary_button_background": "#6f4e37",
    "primary_button_text": "#ffffff",
    "primary_button_border": "#6f4e37",
    "primary_button_hover_background": "#5d3e2c",
    "primary_button_hover_text": "#ffffff",
    "primary_button_hoverd3e2_border": "#5c",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#6f4e37",
    "secondary_button_border": "#6f4e37",
    "secondary_button_hover_background": "#ffffff5c",
    "secondary_button_hover_text": "#5d3e2c",
    "secondary_button_hover_border": "#5d3e2c",
    "input_background": "#ffffff",
    "input_text_color": "#4a4540",
    "input_border_color": "#d4ccc2",
    "input_hover_background": "#ffffff",
    "variant_background_color": "#ffffff",
    "variant_text_color": "#4a4540",
    "variant_border_color": "#d4ccc2",
    "variant_hover_background_color": "#f5ede4",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#d4ccc2",
    "selected_variant_background_color": "#6f4e37",
    "selected_variant_text_color": "#ffffff",
    "selected_variant_border_color": "#6f4e37",
    "selected_variant_hover_background_color": "#5d3e2c",
    "selected_variant_hover_text_color": "#ffffff",
    "selected_variant_hover_border_color": "#5d3e2c"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-2 to warm cream palette"
```

---

### Task 3: Update scheme-3 (Tertiary - Latte Background)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-3 color settings**

Replace scheme-3 settings:

```json
"scheme-3": {
  "settings": {
    "background": "#f5ede4",
    "foreground_heading": "#2d2a26",
    "foreground": "#4a4540",
    "primary": "#6f4e37",
    "primary_hover": "#5d3e2c",
    "border": "#d4ccc2",
    "shadow": "#2d2a26",
    "primary_button_background": "#6f4e37",
    "primary_button_text": "#ffffff",
    "primary_button_border": "#6f4e37",
    "primary_button_hover_background": "#5d3e2c",
    "primary_button_hover_text": "#ffffff",
    "primary_button_hover_border": "#5d3e2c",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#6f4e37",
    "secondary_button_border": "#6f4e37",
    "secondary_button_hover_background": "#ffffff80",
    "secondary_button_hover_text": "#5d3e2c",
    "secondary_button_hover_border": "#5d3e2c",
    "input_background": "#ffffff",
    "input_text_color": "#4a4540",
    "input_border_color": "#d4ccc2",
    "input_hover_background": "#ffffff",
    "variant_background_color": "#ffffff",
    "variant_text_color": "#4a4540",
    "variant_border_color": "#d4ccc2",
    "variant_hover_background_color": "#faf7f2",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#c4a484",
    "selected_variant_background_color": "#6f4e37",
    "selected_variant_text_color": "#ffffff",
    "selected_variant_border_color": "#6f4e37",
    "selected_variant_hover_background_color": "#5d3e2c",
    "selected_variant_hover_text_color": "#ffffff",
    "selected_variant_hover_border_color": "#5d3e2c"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-3 to light latte palette"
```

---

### Task 4: Update scheme-4 (Accent - White with Brown)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-4 color settings**

Replace scheme-4 settings (white background with brown accents):

```json
"scheme-4": {
  "settings": {
    "background": "#ffffff",
    "foreground_heading": "#2d2a26",
    "foreground": "#4a4540",
    "primary": "#6f4e37",
    "primary_hover": "#5d3e2c",
    "border": "#c4a484",
    "shadow": "#2d2a26",
    "primary_button_background": "#6f4e37",
    "primary_button_text": "#ffffff",
    "primary_button_border": "#6f4e37",
    "primary_button_hover_background": "#5d3e2c",
    "primary_button_hover_text": "#ffffff",
    "primary_button_hover_border": "#5d3e2c",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#6f4e37",
    "secondary_button_border": "#c4a484",
    "secondary_button_hover_background": "#faf7f2",
    "secondary_button_hover_text": "#5d3e2c",
    "secondary_button_hover_border": "#6f4e37",
    "input_background": "#faf7f2",
    "input_text_color": "#4a4540",
    "input_border_color": "#c4a484",
    "input_hover_background": "#ffffff",
    "variant_background_color": "#faf7f2",
    "variant_text_color": "#4a4540",
    "variant_border_color": "#c4a484",
    "variant_hover_background_color": "#f5ede4",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#6f4e37",
    "selected_variant_background_color": "#6f4e37",
    "selected_variant_text_color": "#ffffff",
    "selected_variant_border_color": "#6f4e37",
    "selected_variant_hover_background_color": "#5d3e2c",
    "selected_variant_hover_text_color": "#ffffff",
    "selected_variant_hover_border_color": "#5d3e2c"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-4 with coffee accent colors"
```

---

### Task 5: Update scheme-5 (Dark - Footer)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-5 color settings**

Replace scheme-5 (dark theme for footer) with warm dark tones:

```json
"scheme-5": {
  "settings": {
    "background": "#2d2a26",
    "foreground_heading": "#faf7f2",
    "foreground": "#c4a484",
    "primary": "#c4a484",
    "primary_hover": "#faf7f2",
    "border": "#4a4540",
    "shadow": "#000000",
    "primary_button_background": "#c4a484",
    "primary_button_text": "#2d2a26",
    "primary_button_border": "#c4a484",
    "primary_button_hover_background": "#faf7f2",
    "primary_button_hover_text": "#2d2a26",
    "primary_button_hover_border": "#faf7f2",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#c4a484",
    "secondary_button_border": "#4a4540",
    "secondary_button_hover_background": "#4a4540",
    "secondary_button_hover_text": "#faf7f2",
    "secondary_button_hover_border": "#c4a484",
    "input_background": "#3d3a36",
    "input_text_color": "#faf7f2",
    "input_border_color": "#4a4540",
    "input_hover_background": "#4a4540",
    "variant_background_color": "#faf7f2",
    "variant_text_color": "#2d2a26",
    "variant_border_color": "#c4a484",
    "variant_hover_background_color": "#ffffff",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#c4a484",
    "selected_variant_background_color": "#c4a484",
    "selected_variant_text_color": "#2d2a26",
    "selected_variant_border_color": "#c4a484",
    "selected_variant_hover_background_color": "#faf7f2",
    "selected_variant_hover_text_color": "#2d2a26",
    "selected_variant_hover_border_color": "#faf7f2"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-5 footer to warm dark palette"
```

---

### Task 6: Update scheme-6 (Brown - Badges/Highlights)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update scheme-6 color settings**

Replace scheme-6 with coffee brown for badges:

```json
"scheme-6": {
  "settings": {
    "background": "#6f4e37",
    "foreground_heading": "#ffffff",
    "foreground": "#faf7f2",
    "primary": "#faf7f2",
    "primary_hover": "#ffffff",
    "border": "#5d3e2c",
    "shadow": "#2d2a26",
    "primary_button_background": "#faf7f2",
    "primary_button_text": "#6f4e37",
    "primary_button_border": "#faf7f2",
    "primary_button_hover_background": "#ffffff",
    "primary_button_hover_text": "#5d3e2c",
    "primary_button_hover_border": "#ffffff",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#faf7f2",
    "secondary_button_border": "#faf7f2",
    "secondary_button_hover_background": "#5d3e2c",
    "secondary_button_hover_text": "#faf7f2",
    "secondary_button_hover_border": "#5d3e2c",
    "input_background": "#5d3e2c",
    "input_text_color": "#faf7f2",
    "input_border_color": "#c4a484",
    "input_hover_background": "#4a3530",
    "variant_background_color": "#faf7f2",
    "variant_text_color": "#6f4e37",
    "variant_border_color": "#c4a484",
    "variant_hover_background_color": "#ffffff",
    "variant_hover_text_color": "#5d3e2c",
    "variant_hover_border_color": "#faf7f2",
    "selected_variant_background_color": "#faf7f2",
    "selected_variant_text_color": "#6f4e37",
    "selected_variant_border_color": "#faf7f2",
    "selected_variant_hover_background_color": "#ffffff",
    "selected_variant_hover_text_color": "#5d3e2c",
    "selected_variant_hover_border_color": "#ffffff"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update scheme-6 to coffee brown for badges"
```

---

### Task 7: Update Custom Scheme (scheme-58084d4c-a86e-4d0a-855e-a0966e5043f7)

**Files:**
- Modify: `config/settings_data.json`

**Step 1: Update custom scheme color settings**

Replace custom scheme with coffee palette:

```json
"scheme-58084d4c-a86e-4d0a-855e-a0966e5043f7": {
  "settings": {
    "background": "rgba(0,0,0,0)",
    "foreground_heading": "#2d2a26",
    "foreground": "#4a4540",
    "primary": "#6f4e37",
    "primary_hover": "#5d3e2c",
    "border": "#e8e2da",
    "shadow": "#2d2a26",
    "primary_button_background": "#6f4e37",
    "primary_button_text": "#ffffff",
    "primary_button_border": "#6f4e37",
    "primary_button_hover_background": "#5d3e2c",
    "primary_button_hover_text": "#ffffff",
    "primary_button_hover_border": "#5d3e2c",
    "secondary_button_background": "rgba(0,0,0,0)",
    "secondary_button_text": "#6f4e37",
    "secondary_button_border": "#6f4e37",
    "secondary_button_hover_background": "#faf7f2",
    "secondary_button_hover_text": "#5d3e2c",
    "secondary_button_hover_border": "#5d3e2c",
    "input_background": "#ffffff",
    "input_text_color": "#4a4540",
    "input_border_color": "#e8e2da",
    "input_hover_background": "#faf7f2",
    "variant_background_color": "#ffffff",
    "variant_text_color": "#4a4540",
    "variant_border_color": "#e8e2da",
    "variant_hover_background_color": "#f5ede4",
    "variant_hover_text_color": "#2d2a26",
    "variant_hover_border_color": "#d4ccc2",
    "selected_variant_background_color": "#6f4e37",
    "selected_variant_text_color": "#ffffff",
    "selected_variant_border_color": "#6f4e37",
    "selected_variant_hover_background_color": "#5d3e2c",
    "selected_variant_hover_text_color": "#ffffff",
    "selected_variant_hover_border_color": "#5d3e2c"
  }
}
```

**Step 2: Commit**

```bash
git add config/settings_data.json
git commit -m "feat: update custom scheme to coffee palette"
```

---

### Task 8: Verify and Test

**Step 1: Run theme check**

Run: `shopify theme check`

Expected: No errors

**Step 2: Preview changes**

Run: `shopify theme dev`

Expected: Theme loads with new coffee color palette visible

**Step 3: Final commit**

```bash
git add config/settings_data.json
git commit -m "feat: complete coffee color theme update"
```
