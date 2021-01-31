# CSS

Cascade refers to the way the stylesheet processes and assigns weights to rules that apply to the same element, ultimately determining which properties will modify a given element. 

### Origin and Importance
Stylesheets may come from 3 different sources, processed in the following order

- User agent: The browser’s default style sheet.
- User: Such as the user’s browser options.
- Author: This is the CSS provided by the page (whether inline, embedded or external.) 
	- Inline > Internal > External 

### Specificity
when rules within the same stylesheet conflict, the type of selector determines which has more weight

### Rule order
between style rules of identical weight, last one wins

