# MJT_Compare_Spec_Books

## Here is a snapshot so you don't have to comb through the acutal docs.
![Screenshot from 2025-05-27 19-23-32](https://github.com/user-attachments/assets/5c3f4075-9a88-4343-9c88-d319493e5ea0)

Our company was given a new edition of specifications from local Air Force Base that we frequently contract with.
I was tasked with determining what had changed when comparing the old spec book to the new. 
Both spec books were provided in PDF file format. 
### To start, I was told to not exceed half a day in working up a solution. If I didn't succeed, we would review the spec manually. This was great practice with real life deadlines.


## Solution
I saved the PDFS in excel format, isolating each line of text as a singular cell.

I iterated over the 2022 edition and stored each row string value as a key to the 2022 object (or dictionary in VBA terms). The key was stripped of all spaces, grammatical characters, and converted to lowercase to lessen false positives.

To combat boiler plate for text that exists multiple times within the documents, a dictionary was created for each "section" of the document with nested "key":"value" pairs assigned within for each row of text within said section. 
      Here is an example with javascript syntax:
        "
        Section1 : {
          value1: true
          },
        Section2 : {
          value1: true
        }
      "
Next, the 2025 was book was iterated, each row being prepared as a key, and applied to the 2022 dictionary. If the value is undefined, then the line of text has changed in the new spec.

If text changed between editions, the color changes to red. While a touch unrefined, it reliably provides quick access to our project management team.


