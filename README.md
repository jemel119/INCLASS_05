
# CSS Arcade Night · Activity 05

## Team Members

- Team Name: JEREMY & CO
- Member 1: **JEREMY HENRY/002737524**

**Google Doc:** https://docs.google.com/document/d/1XNxarNg4PH1Y8DQhZfPw06Uib9Yr0A-bg0EWK67tKkQ/edit?usp=sharing

## Live URL

**Project Website:** [Insert Live URL Here]

## Build Challenge

**Theme:** Mission Control

I created a one-page Mission Control arcade cabinet using only HTML and CSS.

The project includes all six required CSS checkpoints:

- Flexbox layout for the header and navigation
- A 3 × 3 CSS Grid telemetry dashboard
- Keyframe animations with 0%, 50%, and 100% stages
- Relative and absolute positioning with explicit `z-index` layers
- Hover and `:focus-visible` micro-interactions
- CSS custom properties and responsive design using a `768px` media query

The layered launch section contains smoke, a rocket, and a HUD display arranged using different `z-index` values.

## Round 1 Findings

### Scenario 2 · CSS Grid

A 3 × 3 board is created because `grid-template-columns: repeat(3, 100px)` defines three columns, and the nine cells automatically fill three rows.

### Flexbox Axis

With `flex-direction: column`, the main axis is vertical and the cross axis is horizontal, so `align-items: center` centers the items horizontally.

### Animation Delay

In `animation: moveFraction 3s ease-in-out 1s forwards`, the `1s` value is the delay before the animation begins.

### Animation Ending

Without `animation-fill-mode: forwards`, an animated element returns to its normal CSS state when the animation ends.

### Positioning and z-index

An element using the default `position: static` ignores `top`, `left`, and `z-index`.

## Round 2 Bug Fixes

### Bug 01 · Flexbox Axis

**Problem:** The recipe cards stacked vertically.

**Fix:**

```css
/* 🐛 BUG #1 */
flex-direction: row;
```

`flex-direction: column` made the main axis vertical. Changing it to `row` places the cards side by side.

### Bug 02 · Grid Tracks

**Problem:** The Tic-Tac-Toe board had only two columns.

**Fix:**

```css
/* 🐛 BUG #2 */
grid-template-columns: repeat(3, 100px);
```

Three column tracks create the required 3 × 3 board.

### Bug 03 · Animation Fill Mode

**Problem:** The answer did not use the first keyframe during the delay and lost its final red state after the animation.

**Fix:**

```css
/* 🐛 BUG #3 */
animation: moveFraction 3s ease-in-out 1s both;
```

`both` applies the first keyframe during the delay and keeps the final keyframe after the animation finishes.

### Bug 04 · Stacking and z-index

**Problem:** The heart ignored `top`, `left`, and `z-index`.

**Fix:**

```css
/* 🐛 BUG #4 */
position: absolute;
```

The heart previously used the default `position: static`. Adding `position: absolute` allows its positioning and `z-index` values to work.
