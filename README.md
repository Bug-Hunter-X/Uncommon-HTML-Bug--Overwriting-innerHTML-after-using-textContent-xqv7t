# Uncommon HTML Bug: Overwriting innerHTML after using textContent

This repository demonstrates an uncommon bug in HTML related to modifying content using both `textContent` and `innerHTML`.  The bug occurs when `innerHTML` is used to modify a section of the DOM after `textContent` has already been used to set the text content.

## Bug Description

The bug arises from the unexpected behavior when setting `textContent` and then subsequently using `innerHTML` on the same element. `innerHTML` completely overwrites the DOM structure, discarding any changes made via `textContent`.

## How to Reproduce

1. Open `bug.html` in a web browser.
2. Observe that the text content is initially "This text should be visible.".
3. The JavaScript code first sets the `textContent` and then overwrites it with `innerHTML`. Consequently, only "This text overwrites the previous text." is displayed.

## Solution

The solution involves ensuring that you modify the DOM content consistently using either `textContent` or `innerHTML`, but not both, if you want to add content to existing content, use `insertAdjacentHTML()` or DOM manipulation functions to append or prepend content.