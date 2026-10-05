# How to: Categories & Notes in the Quotation System

A step-by-step guide for managers (Sean, Sharen, admins) and designers.
Local: http://localhost:3000 · Live (after deploy): https://ops.bydesignworks.com

---

## 1. How it fits together

```
Category (main)        e.g. Carpentry
 └─ Sub-category       e.g. Kitchen cabinets
     └─ Items          e.g. Bottom cabinet – $135/ft     ← Master Library
```

- **One list, one place:** categories are created, renamed and given their notes **only** on **Quotations → Categories**.
- **Everywhere else picks from that list:** the Master Library, the quote builder, the PDF and Contractors. None of them can create a category.
- **Managers** set up categories, items and standard notes.
- **Designers** just pick from them when building a quote.

---

## 2. Set up your categories (managers)

**Go to:** Quotations → **Categories**

### Add a main category
1. Type the name in the box at the top, e.g. `Smart Home Works`.
2. Click **+ Add main category**.

### Add sub-categories
1. Click **▶** next to the main category, e.g. **Carpentry**.
2. Type the sub-category name, e.g. `Kitchen cabinets`, and click **+ Add sub**.
3. Repeat for the others, e.g. `Wardrobes`, `TV console`, `Vanity`.

### Change the order
- Use **▲ / ▼** on a category.
- This is the order of the boxes in every new quote and on the PDF, so put them in the order you want clients to read.

### Rename
- Click **Rename** and type the new name.
- Every Master Library item in it follows the new name automatically.
- Quotes already made keep the old name.

### Remove
- Click **Switch off**. The category disappears from pickers, but nothing is deleted.
- Click **Switch on** to bring it back.

### Write the category's notes ("Notes & Specifications")
- **What they are:** the fixed text printed under that category on every quote PDF, e.g. *"All carpentry in E1 grade plywood…"*.
- **To edit:**
  1. Click **▶** on the category.
  2. Type in the **Notes & Specifications** box.
  3. Click **Save notes**.
- It shows **who changed the notes last** and when.

> Each row shows how many items and contractors use it, and who changed it last.

---

## 3. Put items into categories (managers)

**Go to:** Quotations → **Master**

### New item
1. Click **Add Master Scope Item**.
2. **Category:** choose the **main** category (top dropdown), then the **sub-category** (second dropdown). The sub is optional.
3. Fill in the name, description, unit and prices, then save.

### Move an existing item into a sub-category
1. Click **Edit Rates** on the item.
2. Pick the sub-category and save. A small tag with the sub-category name appears under the item.

> **Tip:** do this once for your main items, e.g. all kitchen cabinet items → *Carpentry → Kitchen cabinets*.

---

## 4. Write the standard notes (managers)

**Go to:** Quotations → **Terms**

### Category notes
These are now on **Quotations → Categories** (see section 2). The Terms page only links there.

### Complimentary Inclusions & Remarks (the free gifts)
1. Find the box **Complimentary Inclusions & Remarks (standard)**.
2. Type your usual free gifts and remarks, one per line, e.g.
   ```
   • Complimentary Franke kitchen sink & tap
   • Free whole-house chemical wash before handover
   ```
3. Click **Save standard notes**.
4. Every **new** quotation now starts with this text.

---

## 5. Build a quote (designers)

**Go to:** Quotations → **+ New Quotation** → fill in the client → **Builder**

### The category boxes
- Category boxes appear in the order the manager set.
- Click a box header to **collapse** it when the quote gets long.
- **+ Add Category** lets you pick a category from the list that isn't on this quote yet. To create a brand-new category, ask a manager to add it on the Categories page.
- **×** removes a box you don't need.
- Drag a box, or use **▲ ▼**, to move it on this quote only.
- **Reset Order** goes back to the standard order.

### Add items
1. Click **+ Add Item** in a category box, e.g. Carpentry.
2. Click a sub-category button, e.g. **Kitchen cabinets**, to see only those items. Or type in the search box.
3. Pick the item, then set the room, quantity and rate, and add it.
4. Need something not in the library? Choose **Custom Work** and type your own description.

### Free gifts / remarks
- The **Complimentary Inclusions & Remarks** box is already filled with the standard text.
- Change it for this client if needed. This doesn't change the standard.
- **Use standard notes** puts the standard text back.

### Save
Save, then **Submit for Review**.

---

## 6. What the client sees (PDF)

Open the quote → **Client PDF**:

```
CARPENTRY                                   Subtotal: $8,450.00
  KITCHEN CABINETS
   Kitchen   Bottom cabinet ...   12 FT   $135   $1,620.00
   Kitchen   Top-hung cabinet ... 10 FT   $135   $1,350.00
  WARDROBES
   Master    Full-height wardrobe  8 FT   $350   $2,800.00
  Notes & Specifications: All carpentry in E1 grade plywood…

COMPLIMENTARY INCLUSIONS & REMARKS
  • Complimentary Franke kitchen sink & tap
```

- **Sub-category headings** appear only for items that have a sub-category.
- **Category notes** come from the Terms page.
- **Free gifts** come from that quote's box.

---

## 7. Contractors use the same categories (managers)

**Go to:** Quotations → **Contractors**

- Contractors are grouped under the same main categories, e.g. **Carpentry (13)**.
- **Add a contractor:**
  1. Click **+ Add Approved Contractor**.
  2. Pick their **Category** (their trade) from the list.
  3. If it's not in the list, add it on **Quotations → Categories** first.
- **Cost history:** each contractor's cost records show who recorded each price.

---

## Quick answers

| Question | Answer |
|---|---|
| Where do I add a category? | Quotations → **Categories** (the only place) |
| Where do I put an item under a sub-category? | Quotations → **Master** → edit item → second dropdown |
| Where do I change the text printed under a category? | Quotations → **Categories** → ▶ → Notes & Specifications |
| Where do I set the usual free gifts? | Quotations → **Terms** → Complimentary Inclusions & Remarks |
| Can a designer change free gifts for one client? | Yes, in that quote's builder |
| Can designers edit categories? | No. Managers only |
| If I rename a category, do old quotes change? | No. Only new quotes and the Master Library |
