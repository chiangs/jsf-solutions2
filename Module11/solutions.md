# Module 11 Solutions

<!-- TOC -->

- [Module 11 Solutions](#module-11-solutions)
  - [01 - Forms](#01---forms)
  - [02 - Selecting form fields with JS](#02---selecting-form-fields-with-js)
  - [03 - Form fields and their events](#03---form-fields-and-their-events)

<!-- /TOC -->

[Back to Module 10](../Module10/solutions.md)

## 01 - Forms

1. Create a form with the form tag. Make sure your form has at least one field and a submit button.

```html
<form method="post" action="/some_url">
  <fieldset>
    <label for="first-name">First Name</label>
    <input type="text" name="first-name" id="first-name" autocomplete="first name"></input>
  </fieldset>
  <button type="submit">Submit Form</button>
</form>
```

2. Submit a form by clicking on the submit button and hitting the enter key. Observe what happens. Don't worry if you get a page not found error.

```js
const form = document.querySelector('form')
form.addEventListener('submit', e => {
  // Do something here
  console.log('submitting form')
})
```

3. Prevent a form's default behavior, create console.logstatements after preventing the default behavior, then continue the submission process.

```js
form.addEventListener('submit', e => {
  e.preventDefault()

  // Do stuff here
  console.log('Default prevented. Yay!')

  form.submit()
})
```

[Back to top](#Module-10-solutions)

## 02 - Selecting form fields with JS

`form.elements` is the preferred way to select form fields. 

You can select them by name or id.

fx:
```html
<form>
  <label for="input1">Input 1</label>
  <input type="text" name="input1" id="input1" placeholder="input1">
</form>
```

```js
const form = document.querySelector('form')
const input1 = form.elements.input1;
```

[Back to top](#Module-10-solutions)

## 03 - Form fields and their events


1. Create a text field

```html
<input type="text" name="phone" id="phoneInput" autocomplete="phone">
```

```js
// Get the value of the field when the input event occurs
// Assuming the form has been selected already...
const phoneInput = form.elements.phone;
phontInput.addEventListener('input', e => console.log(e.target.value))
```

```js
// Get the value of the field when the focus event occurs
phoneInput.addEventListener('focus', e => console.log(e.target.value))
```

```js
// Get the value of the field when focusout or blur events occur
phoneInput.addEventListener('focusout', e => console.log(e.target.value))
phoneInput.addEventListener('blur', e => console.log(e.target.value))
```

2. Create five checkboxes

```html
<input type="checkbox" name="checkbox1" id="checkbox1">
<label for="checkbox1">Label for the checkbox1</label>

<input type="checkbox" name="checkbox2" id="checkbox2">
<label for="checkbox2">Label for the checkbox2</label>

<input type="checkbox" name="checkbox3" id="checkbox3">
<label for="checkbox3">Label for the checkbox3</label>

<input type="checkbox" name="checkbox4" id="checkbox4">
<label for="checkbox4">Label for the checkbox4</label>

<input type="checkbox" name="checkbox5" id="checkbox5">
<label for="checkbox5">Label for the checkbox5</label>
```

```js
// Check three of the five checkboxes

```
   -  Get checked checkboxes with JavaScript
   -  Get checked checkboxes when the change event fires
1. Create five radio buttons
   -  Select a radio button
   -  Get the value of the selected radio
   -  Get the value of the selected radio when the change event fires
2. Create a textarea
   -  Get the value of the textarea when the input event occurs
   -  Get the value of the textarea when the focus event occurs
   -  Get the value of the textarea when focusout or blur events occur
3. Create a select dropdown with ten options
   -  Select an option
   -  Get the value of the selected option
   -  Get the value of the selected radio when the change event fires


[Back to top](#Module-10-solutions)

[On to Module 12](../Module12/solutions.md)