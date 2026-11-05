# will-of-d-plan.md format

Check whether the file exists before creating it. If it exists, continue in it and never overwrite it. Keep it light: its purpose is to save the user's time and tokens.

## Template

```
# Plan: <short title>
Status: Draft | Changes requested | Approved

Review this file, then confirm or tell me what to change.

## Goal
<one line>

## Expected output
<concrete description: a wireframe or layout sketch for a UI, sample input and output for code, an outline for a document>

## Flow
<text or Mermaid diagram of how the work will go, start to finish>

## Steps
1. ...
2. ...

## Assumptions and open points
- <things the user should check>
```

## Example (small web task)

```
# Plan: Landing page for a bakery
Status: Draft

Review this file, then confirm or tell me what to change.

## Goal
One-page site that gets visitors to order a cake.

## Expected output
index.html: hero with photo and "Order a cake" button, menu of 6 cakes, contact form, footer. Warm cream and brown palette.

## Flow
```mermaid
flowchart LR
  A[Hero] --> B[Menu] --> C[Order form] --> D[Footer]
```

## Steps
1. Build layout and styles
2. Add menu and form
3. Open in a browser and check every section and the form

## Assumptions and open points
- Using placeholder cake photos until you send real ones (see todo item 1)
```

Rules: update this same file on changes, revise only what changed, and verify the final output against it.
