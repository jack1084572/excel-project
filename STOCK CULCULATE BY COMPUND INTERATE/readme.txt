Sure! Here’s the explanation in **English** for creating row numbers in Excel that **automatically update** when a row is deleted:

---

### **Method 1: Use the ROW() formula**

Assume your data starts from **A2** (A1 is the header). In the serial number column (e.g., column A), enter:

```excel
=ROW()-1
```

Explanation:

* `ROW()` returns the row number of the current cell.
* Subtract 1 because your data starts from row 2. If your data starts from row 1, just use `=ROW()`.

**Pros:**

* Automatically updates when you delete a row.
* Simple and easy to use.

**Example:**

| No.            | Name |
| -------------- | ---- |
| `=ROW()-1` → 1 | John |
| `=ROW()-1` → 2 | Mary |

---

### **Method 2: Use COUNTA() for dynamic numbering**

If you have data in a fixed column (e.g., column B for names), you can use:

```excel
=COUNTA($B$2:B2)
```

Explanation:

* `$B$2:B2` counts from B2 to the current row.
* `COUNTA` counts non-empty cells.
* This ensures continuous numbering even if some rows are empty.

---

### **Method 3: Use Excel Table feature**

1. Select your data range.
2. Insert → Table → check “My table has headers.”
3. Add a “Serial Number” column and enter:

```excel
=ROW()-ROW(Table1[#Headers])
```

* The table automatically fills the formula for all rows.
* Deleting rows will automatically update the serial numbers.

---

✅ **Recommendation:**

* Simple data → Method 1
* Possible empty rows → Method 2
* Data as a structured table → Method 3

---

I can also give you **one formula that handles any row deletion and keeps the numbers continuous**, even with empty rows.

Do you want me to do that?


2.USE $ to LOCK CELL— only if one reference should stay fixed

Example:
If your rate is the same for all rows, e.g. rate = 0.05 in cell B1, then you should lock it with $:

=A2*(1+$B$1)^C2


Now when you drag down:

A2 → A3, A4, etc. (changes)

$B$1 stays locked on the fixed rate

C2 → C3, C4, etc.
