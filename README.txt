BUKHARI TRAVEL — VOUCHER WEB PAGE
==================================

WHAT THIS IS
------------
One web page (voucher.html) that displays any voucher's details, styled
to match your printed voucher. It does not contain any voucher data itself —
it looks up the details from a small data file each time it's opened.

HOW IT WORKS
------------
The voucher number goes in the web address, like this:

  https://yoursite.example/voucher.html?id=BTT-UMR-2026-0716

When that link is opened, the page reads "BTT-UMR-2026-0716" and looks for
a matching file in the "data" folder:

  data/BTT-UMR-2026-0716.json

If found, it displays that voucher's details. If not, it shows a friendly
"voucher not found" message instead of breaking.

ADDING A NEW VOUCHER
---------------------
1. Copy data/BTT-UMR-2026-0716.json and rename it to the new voucher number,
   e.g. data/BTT-UMR-2026-0717.json
2. Open it and replace the details (passengers, flights, hotels, etc.)
   with the new booking's information. Keep the same structure — just
   change the values.
3. Upload that one new file to your hosting (see HOSTING_STEPS.txt).
   You do NOT need to touch voucher.html again — it's reused for every
   voucher.
4. Generate a QR code that points to:
   https://yoursite.example/voucher.html?id=BTT-UMR-2026-0717
   (replace with your real site address and the new voucher number)

FIELDS YOU CAN LEAVE OUT
--------------------------
"transport" and "specialInstructions" are optional — delete them from a
voucher's JSON file (or leave specialInstructions as "") if not needed.

TESTING BEFORE YOU HOST
------------------------
You can preview this on your own computer before putting it online:
1. Keep voucher.html and the data folder together in one folder.
2. On Windows: open a Command Prompt in that folder and run
     python -m http.server 8000
   On Mac: open Terminal in that folder and run the same command.
3. Open a browser and go to:
     http://localhost:8000/voucher.html?id=BTT-UMR-2026-0716
   (Opening voucher.html directly by double-clicking will NOT work —
   it needs to be served, which is also true once it's hosted online.)
