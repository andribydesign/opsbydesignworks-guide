# Quotation System — Manual Test Checklist (start to end)

By Design Works · ops.bydesignworks.com · prepared 5 Oct 2026

How to use: follow the sections in order — they walk one real renovation job from enquiry to final variation
order, the way it happens in the business. Tick each box only when the **Expected** result matches. Write the
quote number and anything odd in the notes column.

> **Before you start**
> - Use **test data only**: client name starting with `TEST`, phone `+65 9000 0000`. Never test on a real client's quote.
> - You need two logins: a **manager** (Sean / Sharen / admin) and an **Interior Designer**. An admin can use
>   **View as → Interior Designer** in the header for the ID steps.
> - Items marked **🆕** are in the 05-09 feedback release (branch `fix/quote-0509`) — test them after that release is live.
> - Rates on live are still **dummy** until the real rate sheet is imported.

---

## 0. One-time setup (manager)

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | Quotations menu → **Companies** 🆕 (managers; or `/quotations/companies`): check company #1 (name, UEN, address, phone, email, bank, account no., PayNow QR) | All details correct; marked **default** | |
| ☐ | Add the **second company** with its own UEN and bank account | Saved; appears in the list; still exactly one default | |
| ☐ | Quotations → **Master Library**: search an item by word (e.g. "grout") | Matching items show | |
| ☐ | Add a new master item (category, name, description, unit, prices) 🆕 | Success message **and** the item appears in the list and in search straight away | |
| ☐ | Open an item → per-list prices (BTO / Resale HDB / Condo / Landed / Commercial) | Each list shows its own price | |
| ☐ | Quotations → **Terms & Conditions**: master terms and payment schedule present | Text reads correctly, no `???` characters | |

## 1. Lead → new quotation (ID)

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | From a TEST lead at Proposal stage, start a new quotation (or Quotations → **+ New Quotation**) | Form opens; if from a lead, client details are pre-filled | |
| ☐ | Fill client name, phone, email, project address | — | |
| ☐ | NRIC field: type a full NRIC `S1234567D` 🆕 | After saving, only **•••••567D** is shown anywhere (PDPA: last 4 kept) | |
| ☐ | **Property type** dropdown | Exactly the 8 options with the agreed spelling (BTO 8.5Ft ceilin height … Commercial (9ft)) | |
| ☐ | **Issuing company** dropdown 🆕 (only when 2+ companies) | Default company pre-selected | |
| ☐ | Pick a **template** (e.g. HDB Resale Full Overhaul) → **Initialize quote & open builder** | Builder opens with the template's lines priced from the chosen property type's list | |
| ☐ | Create a second TEST quote with the **same template but a different property type** (e.g. Landed) | Line prices differ between the two quotes | |

## 2. Building the scope (ID)

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | **+ Add item** in a category (e.g. Carpentry) from the Master Library | Description, unit and unit price fill in from the library | |
| ☐ | Change quantity | Line total and category subtotal update | |
| ☐ | Change a unit price away from the standard | A **reason is required**; saved with the reason | |
| ☐ | Add a **custom item** (not in library) | Saves with your description and price | |
| ☐ | Mark one line **FOC**, one **KIV**, one **Optional** | FOC shows $0 to client; KIV / Optional excluded from total but listed | |
| ☐ | Room / area per line (Kitchen, Master Bedroom …) | Shown on the line and in the PDF | |
| ☐ | Add a **discount** with reason; toggle **GST** | Totals recalculate; GST shown separately when on | |
| ☐ | **Save draft**, leave, reopen | Everything kept | |
| ☐ | Wait 30 s without saving | "Auto-saved" appears | |
| ☐ | As ID: the cost / GP / margin figures | **Hidden** for the ID; visible for managers | |

## 3. Price requests (ID → manager) 🆕

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | Quotations → **Pending Prices** → submit a custom trade quote for **your TEST quote** (category, description, cost, unit) | Appears as Pending, "For Q-…" shown | |
| ☐ | Manager: **One-Off** — enter a **selling price** first | Cannot approve without a selling price; after approval shows "sell $…" | |
| ☐ | **+ Add to quote** on the one-off | Message "Added to Q-… as a custom line"; the line is in the quote's draft at that price | |
| ☐ | Manager: **Archive** an old one-off | Disappears from the active list (kept on record) | |
| ☐ | Manager: **Promote to Master** another request | Item added to the Master Library in the chosen category and found by search | |

## 4. Review & approval

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | ID: **Submit for review** | Status *Ready for review*; managers get a Telegram alert; quote counts in "Ready for Review" | |
| ☐ | ID (or admin "View as ID"): open the quote | **No Approve / Return buttons** for the ID 🆕 | |
| ☐ | Manager: **Return with notes** | Status *Revision required*; ID sees the notes and gets an alert; it tops **My Day → My quotations** | |
| ☐ | ID fixes and re-submits; manager **Approves** | Status *Approved*; ID alert; the old "manager review feedback" banner no longer suggests a rejection | |

## 5. The client PDF (check carefully — this is what the client sees)

Open **Client PDF**, then Print → Save as PDF (Chrome/Edge, untick *Headers and footers*).

| ✓ | Check | Expected | Notes |
|---|---|---|---|
| ☐ | Header | Issuing company's **name, address, phone, email, UEN** 🆕 (second company if chosen) | |
| ☐ | Client block | Name, phone, email, address, property type; NRIC as •••••567D | |
| ☐ | Each category | Category title + **Subtotal $X**; rooms, descriptions, qty, unit, unit price, amount | |
| ☐ | Totals | Subtotal, discount, GST (if on), **grand total** equal the screen | |
| ☐ | Page breaks | A category or a T&C clause is never cut across two pages; table headers repeat | |
| ☐ | Footer | "Page X of Y" on every page; no browser URL/date | |
| ☐ | Payment schedule & bank | Milestones add up to 100%; the **issuing company's** bank/PayNow details | |
| ☐ | Terms & conditions, exclusions, client-supplied items | Present and readable; no `???` | |
| ☐ | Signature blocks | Client and company signatures present | |

## 6. Present, client feedback, revisions

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | Manager: **Mark presented** (choose channel) | Version locked; status *Presented* | |
| ☐ | Client asks for changes → **+ Revise (v2)** | v2 opens as a draft copy; v1 kept | |
| ☐ | Change 2–3 lines (qty, price, remove one, add one) → submit → approve → present | — | |
| ☐ | **Version history** → *Compare with v1* 🆕 | Only the lines you actually changed show as added / removed / adjusted, with correct amounts (no "everything removed + added") | |
| ☐ | **View PDF** on v1 | Old version's PDF opens, marked superseded | |
| ☐ | Linked lead (if the lead–quote link is On in Settings) | Lead shows the quote number, version and latest value | |

## 7a. Outcome A — client does NOT sign 🆕

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | Manager on the presented quote: **Client not proceeding? Mark this quote lost** → reason + note | Red **Lost** banner with reason; quote listed under the **Lost** filter | |
| ☐ | Linked lead | Lead closed as **Lost** with the same reason; lost value recorded | |
| ☐ | **Reopen quote** | Back to *Presented* | |
| ☐ | Close a different TEST lead as Lost from the CRM | Its unsigned quotes become Lost; reopening the lead brings them back | |

## 7b. Outcome B — client signs

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | Presented quote: the green **"✓ Client signed? Confirm ↓"** button at the top 🆕 | Jumps to the sign-off box | |
| ☐ | **Lock as signed contract**: payment reference + upload the signed contract (PDF or photo) | Status *Signed & Paid*; "View Signed Contract" opens the file | |
| ☐ | Only one version is signed 🆕 | Version history shows one *Accepted*; earlier ones *Superseded* | |
| ☐ | **+ Revise** is gone; only a manager sees **Re-quote signed contract…** (reason required) 🆕 | ID cannot revise a signed contract | |
| ☐ | On the lead: **Mark signed** with the contract value | Lead *Signed*; revenue in Reports | |

## 8. Variation orders (after signing)

| ✓ | Step | Expected | Notes |
|---|---|---|---|
| ☐ | **+ Create variation order** | VO01 opens as draft; baseline = signed contract sum | |
| ☐ | Add **several additions** (library item and custom) | All lines kept after **Save & Submit** | |
| ☐ | Add a **deduction** of a signed-quote item | Shown as a negative line | |
| ☐ | Choose a **payment terms** preset; edit the VO **terms** | Saved on this VO only | |
| ☐ | Submit → appears in **Ready for Review** with a "VO review" tag 🆕 | Manager alerted | |
| ☐ | Manager approves → presents | — | |
| ☐ | Client wants a change → **+ Revise (R2)** 🆕 | VO back to draft as R2; **Revision history** shows R1 with its lines | |
| ☐ | Re-submit → approve → present → **accept** with the client's signed VO uploaded | VO *Accepted*; signed copy opens | |
| ☐ | Quote page | **"Contract incl. 1 VO"** = signed sum + VO net, with updated margin (managers) 🆕 | |
| ☐ | Create **VO02** | Shows **Previously Approved VOs** and **Contract Sum Prior to VO02** = signed sum + VO01 | |
| ☐ | In VO02, deduct an item that was **added in VO01** 🆕 | "[VO01] …" items are in the deduction list | |
| ☐ | Create VO03 → approve → **Cancel / void** with a reason | *Cancelled*; VO PDF marked **VOID**; not counted in the contract sum | |
| ☐ | VO PDF | Issuing company, baseline, previously approved VOs, additions/deductions, net, payment terms, T&C, signatures | |

## 9. Permissions (repeat as ID via "View as")

| ✓ | Check | Expected |
|---|---|---|
| ☐ | ID: create, build, submit, revise own unsigned quotes | Allowed |
| ☐ | ID: approve, return, present, sign, mark lost, change company, re-quote signed | **Not shown / refused** |
| ☐ | ID: cost, GP, margin | Hidden |
| ☐ | Marketing staff: Quotations menu | Not shown unless granted |

## 10. Phone check (real phone)

| ✓ | Check | Expected |
|---|---|---|
| ☐ | Quotes list, one quote, one VO | No sideways scrolling; totals visible at the top; action buttons reachable |

---

### Sign-off

| Tested by | Date | Release / tag | Result (pass / issues found) |
|---|---|---|---|
| | | | |

**Known limits while testing:** dummy rates; the lead–quote link may be **Off** in Settings (then lead
sync steps don't apply); old version comparisons made before the 05-09 fix may still show wrong +/−.
