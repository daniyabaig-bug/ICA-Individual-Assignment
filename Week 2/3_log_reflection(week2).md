AI CODE EVALUATION

Step 3:
## AI Code Evaluation (Step 3)

1.`raw.info()` – KEEP: This code correctly displays the dataset's information, including column names, data types and non-null values.

2.`raw.isna().sum()` – KEEP: This code correctly identifies and counts missing values in each column.

3. `raw.duplicated().sum()` – KEEP: This code correctly counts the number of duplicate rows in the dataset.

4. `raw[raw.duplicated(keep=False)]` – KEEP: This code displays all duplicated rows, allowing us to examine them.

5. `pd.to_numeric(raw["price"], errors="coerce")` – MODIFY: This code converts prices into numeric values, but treats prices containing commas, such as 1,250, as missing values. The commas should be removed before conversion.

6. `clean = raw.copy()` – KEEP: This creates a separate copy of the original dataset and protects the raw data from changes.

7. `raw["item"].value_counts()` – KEEP: This code shows the frequency of each item and helps identify inconsistent item names.

8. `raw.drop_duplicates()` – REJECT: This code does not permanently remove duplicates because the result is not assigned back to the dataset.

9. `clean = clean.drop_duplicates()` – KEEP: This correctly removes duplicate rows from the cleaned dataset.

10. `clean["item"] = clean["item"].astype(str).str.strip().str.title()` – KEEP: This removes unnecessary spaces and standardises item names using title case.

11. `clean["price"] = pd.to_numeric(...)` – KEEP: This correctly removes commas from price values and converts them into numeric format.

12. `clean = clean.drop_duplicates()` – REJECT: This repeats the duplicate-removal process unnecessarily because duplicates were already removed earlier.

13. `c` – REJECT:** This code refers to an undefined variable and produces an error. It should be removed.

14. `print(clean.head())` – KEEP: This displays the first five rows of the cleaned dataset.

15. `print(clean.isna().sum())` – KEEP: This checks the number of missing values remaining after cleaning.

16. `print(clean.duplicated().sum())` – KEEP: This verifies whether any duplicate rows remain after cleaning.

Step 4: Reflection

1. Which decisions did I make differently from AI?

I decided not to automatically delete suspicious prices or fill in missing values. I kept these observations because there was insufficient evidence to determine whether they were incorrect. I also identified unnecessary and incorrect lines of code during the evaluation.

2. Which of my decisions were better supported by evidence?

My decision to retain missing and suspicious price values was supported by the dataset because I could not confirm their actual values. Removing exact duplicate rows and standardising item names were also supported by the evidence.

3. What would I have missed if I had worked alone?

Without AI, I might have missed some useful data-cleaning techniques and efficient ways to identify inconsistencies. AI helped me understand different approaches, but I still needed to check its suggestions because some code was unnecessary or required modification.

Conclusion:

This assignment taught me that AI can assist with data cleaning, but its suggestions should not be accepted blindly. Every cleaning decision should be supported by evidence, and the original dataset should always be preserved.
