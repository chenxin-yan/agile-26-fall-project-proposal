# Split

A web app you open on your phone to split the bill after a dinner or a trip. Add the receipts, send your friends a link, and everyone sees who owes whom.

## What and why?

Every group dinner ends the same way. One person pays, and for the next week the group chat is "wait, how much do I owe you?" Somebody opens the calculator app, somebody screenshots the receipt, and two people never pay because they forgot.

I've tried the existing tools and they don't fit this. Splitwise is built for roommates who share rent for a year, not five people who had one dinner. It makes every person sign up before they can even see their share. The free tier caps how many expenses you can add per day, and receipt scanning is behind a paywall. Venmo and Zelle move the money but do nothing to figure out the amounts. So we end up back at the calculator and the group chat, and the numbers get buried in the scroll-back.

Split is for the one-off event. One person makes the event and shares a link. Everyone else taps it, types their name, and they're in. Receipts get added as they happen, by photo or by typing the total, and the app keeps a running tally across all of them. When it's time to settle, everyone pays their net amount however they normally would and marks it paid.

I don't want to build a payment app. I want nobody to do arithmetic in a group chat again.

## For whom?

Students who split costs with friends. Dinners out, groceries for a party, gas and an Airbnb on a trip. The first users are my own friend group and my classmates in this course. We split something almost every week and none of us use Splitwise, because it's too much setup for one dinner.

They're easy to get feedback from. Every weekend dinner or trip is a test.

## How?

The organizer signs up with an email and password, creates an event like "Ski trip Feb 14," and gets a link to share.

A participant opens the link, types their name, and is in. No account. They get a personal link they can bookmark or re-open from the group chat, and that link identifies them on any device. If two people both type "Jake," the organizer can rename or merge them.

Anyone in the event can add a receipt. Take a photo and the app uses AI to read the total and the merchant, or just type the total. Each receipt records who paid and who's included. Everyone is included by default. Optionally, uncheck the friend who skipped dinner. The receipt splits equally among the people included, or by percentage if the group wants something uneven. A trip can have as many receipts as it produces.

The event page shows every receipt and a live balance for each person: what they paid, what they consumed, and what they owe or are owed. A settle-up view turns those balances into a short list of payments, like "Jake pays Sam $37." A toggle shrinks it to the fewest possible transfers, so five people don't need ten payments.

When Jake actually pays Sam over Zelle, Jake taps "I paid." Sam sees it as pending and taps "confirm." The line clears. Pending payments are visible to everyone, so nobody pays twice.

When it's all settled, the organizer closes the event. No more receipts can be added, so the numbers people paid against can't change afterward. The organizer's account keeps a list of past events.

## Scope

The core has organizer login, event and receipt management, image upload, an AI receipt-reading step with a manual fallback, link-based identity for people without accounts, an algorithm that turns receipts with different payers and different participants into per-person balances, a transfer-minimizing algorithm, and a two-step settlement flow. All of it has to work on a phone in a browser. That fills five sprints for four to six people.

It also isn't too ambitious. I cut the parts that sink projects like this. No payment processing means no bank APIs and no liability. No persistent groups, no per-item claiming, no multi-currency, no notification system.

If there's time left: live updates so everyone's tally refreshes when a receipt lands, and a one-tap export of the final summary as an image for the group chat.
