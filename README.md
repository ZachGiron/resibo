# Resibo

A restaurant bill calculator for the Philippines. Split a bill between diners and apply senior citizen and PWD discounts, VAT and service charge. It is free, works on phones and computers, installs like an app, and works offline.

**Live app:** https://ZachGiron.github.io/resibo/

## What it does

- Splits one bill between any number of diners, with a separate total for each person
- Applies the senior citizen or PWD discount (20% by default) and VAT exemption to that person's own share only
- Lets you choose which items get the discount for each senior or PWD diner, in case the restaurant discounts only certain items
- Adds VAT and service charge, with rates you can change
- Shows a receipt-style breakdown: VATable sales, VAT, VAT-exempt sales, discounts, service charge and total due
- Copies a short summary you can paste into a chat
- Remembers your bill on your device and works without an internet connection

## How to use

1. **Add diners.** Enter a name for each person and choose Regular, Senior citizen, PWD or Custom. Custom lets you set your own discount percentage and say whether it is VAT-exempt.
2. **Add orders.** For each item, enter the name, quantity and price of one. Tap the names under "Shared by" to choose who ate it. A dish shared by several people is divided equally between them.
3. **Choose what gets the discount.** Under each item, the "Discount for" buttons list the senior and PWD diners sharing it. A tick means the discount applies, and everything is ticked by default. Tap a name to turn it off for that item. That diner then pays the listed price, VAT included, for it.
4. **Review the settings.** Open "Rates and rules" to match the restaurant's VAT, discount and service charge.
5. **Read the receipt.** Each diner's amount is under "Pays", and the bill total is at the bottom. Use "Copy summary" to share it.

"Start fresh" clears the sample order and starts a new bill.

## How the amounts are worked out

Prices are assumed to include VAT unless you turn that setting off.

**Senior citizen or PWD, ₱1,000 of discounted items, 10% service charge on the menu price**

| Step | Amount |
| --- | ---: |
| Menu price, VAT included | ₱1,000.00 |
| Remove VAT (divide by 1.12) | ₱892.86 |
| Less 20% discount | −₱178.57 |
| Food after discount, no VAT | ₱714.29 |
| Service charge, 10% of ₱1,000 | ₱100.00 |
| **Pays** | **₱814.29** |

**Regular diner, ₱500 of food, 10% service charge**

The ₱500 already includes ₱53.57 of VAT. Service charge is ₱50.00, so the diner pays ₱550.00.

**Senior citizen with ₱600 of discounted items and ₱400 of items with the discount turned off, no service charge**

The ₱600 becomes ₱428.57 after VAT removal and the 20% discount. The ₱400 is charged as listed. The diner pays ₱828.57.

Other details:

- Every person's amounts are rounded to the nearest centavo, and the bill total is the sum of what each person pays, so the numbers always add up.
- When a shared dish does not divide evenly, the leftover centavos go to some of the people sharing it, so the shares always add up to the item's price.
- Items that no one is assigned to are not included in the total, and the app warns you.

## Settings

| Setting | Default | What it does |
| --- | --- | --- |
| VAT % | 12 | Rate used to remove VAT from listed prices, or to add it |
| Senior / PWD discount % | 20 | Discount for Senior citizen and PWD diners |
| Service charge % | 10 | Added to each diner's bill |
| Menu prices already include VAT | On | Turn off if the menu shows prices before VAT |
| Service charge is computed on | Menu price, before any discount | Or "Amount after the discount", the food actually charged |

Restaurants handle service charge differently, so set it to match the printed receipt.

## Install it as an app

**Chrome or Edge on a computer:** open the app, click **Install app** at the top of the page (or the install icon in the address bar), then confirm.

**Android (Chrome):** open the app, tap **Install app** at the top of the page (or the ⋮ menu, then **Install app**), then confirm.

**iPhone or iPad (Safari):** open the app, tap the **Share** button, choose **Add to Home Screen**, then tap **Add**.

Open the app once while you are online so it can save itself. After that it works without a connection.

## Privacy

Everything runs on your device. Your bill is saved in your browser's local storage and is never sent anywhere, and the app makes no requests to other sites other than loading its fonts. Saved bills do not sync between devices, and clearing your browser's site data removes them.

## Limits and disclaimer

- Resibo is a calculator. It is not an official receipt, and it does not check anyone's eligibility or ID.
- It is not tax or legal advice. Which items a restaurant discounts, and how it treats service charge, vary, and rules can change. Check current BIR and DTI guidance, or ask the restaurant, if you are unsure.
- Shared dishes are always split equally between the people sharing them.
- The discount is applied to a whole item, not to part of a quantity. If a restaurant discounts only one of three of the same dish, enter that one as its own line.
- Because the bill is stored per browser, a bill started on one device will not appear on another.

## Built with

Plain HTML, CSS and JavaScript. No frameworks, no tracking, no account. Offline support uses a service worker, and the app can be installed as a progressive web app (PWA).
