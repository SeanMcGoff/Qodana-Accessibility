# Qodana Accessible Form

The goal of this project was to create a registration form that was compliant with [WCAG-2](https://www.w3.org/WAI/standards-guidelines/wcag/). In order to focus more on the accessibility rather than the tech stack, I'm only using HTML5, vanilla JS, Tailwind CSS, and Github Pages to host this. Here are some of the ways that I have made this form accessible:

- High Contrast 
  - The minimum contrast of any background/text is 8.19:1, which is over the WCAG's AAA metric of 7:1
- Clearly Indicating Focused Elements
  - This was done by adding a ring of blue to every element of the form when that element is focused
- Semantic Tag Use
  - Every input is clearly an input for a screen reader since \<input\> is used. The header of the page is shown to be the header via an \<h1\>.
- Labels for every form input
  - This is done with a \<label\> tag and the *for* attribute linking each label to the corresponding input
- *aria-label* attributes
  - The *aria-label* attribute is given to every element of the page so that someone using a screen-reader can better navigate the page.
- Autocomplete
  - Email, Username, and Password forms are marked accordingly using the "autocomplete" tag, allowing browsers and/or extensions to autofill data if possible
- Password Requirements
  - On the initial loading of the page, the rules of the password form are not visible. As one types a password, they appear when the requirements are not met. This can pose a problem for screen readers as someone who is vision-impaired might not be able to see the password requirements. This is solved in multiple ways:
    - Using the *aria-describedby* attribute, a screen reader will read aloud the password requirements on selection of the password input box.
    - While the requirements appear hidden on initial load, I am taking advantage of tailwind's *sr-only* class which hides elements from the user but not screen readers
    - As password requirements are met, I am then adding the hidden class name to those elements so that on a rejection of password, a user will know exactly which password requirements they haven't met. 
