# Weather Application

Creating a simple weather application using JSON, Ajax and CSS.

## 1. BUILD A REQUEST
- Define an object that holds the `q`, `units` and `APPID` variables. The variables can start with the following default values (already defined for you):
  - 'q':city                                      // the city you live in
  - 'units':'metric'                              // or some other unit
  - 'APPID':'6dec5fb891e6e243c9d8c20351998e67'    // a key
- Pass the new Object to the host via the second argument of the `getJSON()` call, which takes information about the request
- Check the `result` data that returns by using the log()
    - How do we access the current temp variable?
    - What other kind of data is useful?

## 2. SETUP THE INTERFACE
- Build a `<form>` with an `<input type="text">` and a `<button type="button">`, center it and `position` it at the top of the viewport
  - Remember: if you don't want the gap between the button and input, they will have to float
- Find a custom block-style font that is heavy and apply it to an `<h1>` that will hold the `.location` being displayed and `position` it at the bottom of the viewport
- Create a div to hold the temperature for `.today`, that has a `.current`, `.high` and `.low` and vertically center it in the viewport

## 3. DISPLAYING THE TEMP
- From the `.getJSON()` call-back, put the `data.main.temp` value into the `.current` element
- Do the same for the `temp_min` and `temp_max` values into `.low` and `.high`
- Define a classes for `.hot` and `.cold` temperatures that will change the `background-color` of any elements they are applied to
- Ensure the `background-color` of the body will `transition` over a period of time
- Setup an if-else statement block that will apply `.hot` to the `body` if the temp is above 10, `.cold` if below -10 and neither if in between

## 4. CITY-WEATHER SEARCH
- Write and test a `.click()` listener for the `<button>`
- When clicked, take the `.val()` from the `<input>` and set it as the city (`q`) value and re-run the `getJSON()` request
- Note you may have to reorganize the structure of this document

## EXTRAS (TAKE HOME RESEARCH):
- Use `navigator.geolocation.getCurrentPosition(function(position) {})` to get your current coordinate and search using that
- Use `localStorage.setItem('city', 'Toronto')` to store the current city value
  - You can also us an array to store your search history
- Colour the background relative to the temperature
  - For example: Red can be calculated between -25.5 and 25.5 using this:
      'rgb(255, '+(255-(temp*10))+', '+(255-(temp*10))+')'
- Use the included M e t e o c o n s   icon fonts to add icons relative to the weather
- Create an element with the class of time to see a live clock show up (date.js)
