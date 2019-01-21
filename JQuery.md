# JQuery

`const searchInput = document.querySelector('.search');` # => id
`const suggestions = document.querySelector('.suggestions');`

`document.querySelectorAll("p")` => select all with  <p>
`document.querySelectorAll("div.note, div.alert")` => select all <div> within doc
with a class of `note` and `alert`

`container.querySelectorAll("div.highlighted > p")` => get <p> element whose
immediate parent element is a `div` with the class "hightlighted"


`searchInput.addEventListener('change', displayMatches);` // change is an event
`searchInput.addEventListener('keyup', displayMatches);` // keyup is an event

checkout this link
https://johnofsydney.gitbooks.io/wdi-28/week_02/wk02_day04.html
