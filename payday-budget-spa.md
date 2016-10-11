# Payday Budget SPA

####a web-based personal finance app for those who live paycheck to paycheck

*This is an entry in the [func-specs blog series](http://samhatfield.me/tag/func-specs).*

## The Setup

There have been many times in my life when money was tight, and the goal was
simple: make it to the next payday. My lovely wife had a similar situation, and
she developed her own system. She implemented it in a spreadsheet application,
which meant she had to do lots of manual steps, and she often had to keep track
of stuff in her head while she was away from the data. She's *way* better than
this than I could ever be, but sometimes she, like anybody else, would miss
something, and that caused short-term and long-term anxiety. I convinced her
that switching to a more automated system would be better for keeping track of
everything, and she agreed.

There were/are problems. Our CU doesn't have a native app, and their mobile
version of their website isn't good for balance glancing. There are many
non-institution apps for Android, but they all require manually entering in
transactions, and only some of them sync across multiple devices. Most
importantly, not a single one of them fit the personal finance model that my
wife created.

## The Solution: Payday Budget SPA

This project, with the "creative" name of Payday Budget SPA (SPA = single page
app, for those of you not in the know), is meant to solve the problems of using
a manual system in a spreadsheet or in existing mobile apps. At first, the
project is going to be fairly tailored to our use case. But, I think it could
be a personal finance app for anyone that don't know accounting, but do know
how much money they have, and how long it has to last.

### Overview

Payday Budget SPA helps users keep track of their balance and spending in
between paydays. It works for people that live paycheck to paycheck and have to
manage money in sprints instead of marathons.

The app has three inputs: the dates of your paydays, how much you get paid, and
a list of transactions. The list of transactions work like many other personal
finance apps: time, amount, payee metadata, and other notes.

Based on the current date, the dates of your previous and next paychecks, and
the amounts of the transactions in between those dates, the app calculates how
much disposable money you have *right now*. This is the main output of the app,
to help people manage decisions about what they can and cannot afford to do
*right now*.

### A Scenario, with made-up numbers

Let's say that it's the weekend, and you are trying to figure out if you can
take your family out to dinner, or cook spaghetti (again). Let's say you get
paid $1k every two weeks, and this is the off week. You have payments for your
phone bill, car insurance, and groceries that you've already made ($680), and
those automatic payments for Netflix and Gwinnie Bee ($120) are coming out on
Tuesday.

The restaurant bill is going to be around $40 bucks, because **kids need
milkshakes with dinner** and you tip well. You want to konw if you can spend
that kind of money right now. So, you look at your budgeting app.

If we were using a traditional personal finance app, the balance that it would
report would likely be $680. The future transactions for the automatic payments
are in there, but they won't be recorded as spent money until Tuesday. If you
forget about the automatic payments (and who hasn't?), you'd calculate in your
head that you have about $300+, until next Friday. When you remember about
those payments, it'll definitely be *after* the milkshakes are ordered, and not
a moment before.

With Payday Budget SPA, the balance would be reported as "$200 until next
Friday," which is less than your bank account would report, but that money is
as good as spent. Better heat up the spaghetti sauce. Sure, it's the third time
this week, but at least you won't have a money-induced panic for dessert.

### What this app won't be

This app is not meant to replace traditional budget software. It is not
designed to help people  with long-term goals. It's not going to be useful for
accountants or rich people.

### The details

include a list of things that you want to add to the budget sometime in the
future, but don't know exactly when you can afford it
the UI would present budget items to add to each paycheck with drag/drop and
keyboard options

Data Models:

- PayDay
  - this represents a pay day, the unit of organization in this app.
  - it holds data about how much a payday is, and how often it occurs
- Transaction
  - this represents you spending money on something
  - records date, amount, and meta data like payee and notes
