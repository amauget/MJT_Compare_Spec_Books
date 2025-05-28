# MJT_Compare_Spec_Books

Our company was given a new edition of specifications from local Air Force Base that we frequently contract with.
I was tasked with determining what had changed when comparing the old spec book to the new. 
Both spec books were provided in PDF file format. 
### To start, I was told to no exceed half a day coming up with a solution. If I couldn't do so, we would review the spec manually. This was great practice with real life deadlines.


## Solution
I saved the PDFS in excel format, isolating each line of text as a singular cell.

I iterated over the 2022 edition and stored each row string value as a key to the 2022 object (or dictionary in VBA terms). The key was stripped of all spaces, grammatical letters, and converted to lowercase to prevent false positives.

To combat boiler plate for text that exists multiple times within the documents, a dictionary was created for each "section" of the document with nested "key":"value" pairs assigned within for each row of text within said section. 
      Here is an example with javascript syntax:
        Section 1 : {
          value1: true
          },
        Section 2 : {
          value1: true
        }
Next, the 2025 was book was iterated, each row being prepared as a key, and applied to the 2022 dictionary. If the value is undefined, then the line of text has changed in the new spec.

If text changed, its color is changed to red. While a touch unrefined, it reliably provides quick access to our project management team.

## Here is a snapshot so you don't have to comb through the acutal docs.
![Screenshot from 2025-05-27 19-23-32](https://github.com/user-attachments/assets/5c3f4075-9a88-4343-9c88-d319493e5ea0)
