# Project 15 - LocalStorage

## Demo

https://andycodes.io/JavaScript30/15%20-%20LocalStorage/

## Objective

---

For project 15, I learned about LocalStorage and Event Delegation. We build a list of tapas with a checkbox to marked if the guest has received their tapas. We are able to reload the page and the tapas that was order as well as if they received it is still on the list, this is done by saving the information in local storage.

## Local Storage

### Saving to local storage

To save information to local storage we use `localStorage.setItem('items', JSON.stringify(items));`

1.  The first parameter `'items'` is the key
2.  The second parameter is a string of the `items` object using `JSON.stringify`

### Get items from local storage

To get information from local storage we use `const items = JSON.parse(localStorage.getItem('items')) || [];` when we initialize the items array

## Event Delegation

---

```
const itemsList = document.querySelector('.plates');

itemsList.addEventListener('click', toggleDone);

function toggleDone(e) {
  if (!e.target.matches('input')) return; // skip this unless it's an input
  const el = e.target;
  const index = el.dataset.index;
  items[index].done = !items[index].done;
  localStorage.setItem('items', JSON.stringify(items));
  populateList(items, itemsList);
};

```

This is how was used event delegation in this application, we added a click event listener to the unordered list and to check if they clicked on the checkbox, we `if (!e.target.matches('input')) return;`

The idea to think about event delegation as responsible parents (ul) and negligent children (li) who don't hear any instructions from the parents. So the parent the responible one, has to tell it what to do

## Javascript

A trick to toggle an boolean statement is go set it to the not operator (!) `items[index].done = !items[index].done;`
