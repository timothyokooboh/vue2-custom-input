# vue2-custom-input
A custom input component NPM package for Vue2 applications

## Installation
*npm install vue2-custom-input*

## Usage
`import CustomInput from "vue2-custom-input"`

`export default {
  components: {
    CustomInput
  }
}`

`<custom-input></custom-input>`

By default the input element takes the full available width. 

`<form style="max-width: 30rem"><custom-input></custom-input></form>`

## v-model
The custom-input component uses v-model to create *two-way data binding*.
`<custom-input v-model="email"></custom-input>`

## Props
* **type**.
Default is **text**. E.g email, number
`<custom-input type="email"></custom-input>`

* **label**.
E.g **Email address**
`<custom-input label="Email address"></custom-input>`

* **placeholder**.
E.g **Email address**
`<custom-input placeholder="Email address"></custom-input>`


* **id**.
Used to set **id** attribute on the input element. It is also dynamically bound to the **for** attribute of the label element.
`<custom-input id="email"></custom-input>`

* **srOnly**.
Used to specify whether the *label* should only be visible to screen readers.
Default value is false.

`<custom-input srOnly></custom-input>`

* **color**.
Used to set the border color of the input element
`<custom-input color="blue"></custom-input>`

* **required**.
Used to specify whether a value is required.
Default value is *true*
`<custom-input :required="false"></custom-input>`

