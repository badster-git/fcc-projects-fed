<div align="center">

# My FreeCodeCamp Projects

### Table of Contents

| Project | About |
| -------- | --------- |
|     | **Data Visualization** |
| [U.S. GDP Bar Chart](https://codepen.io/badster-pen/full/jOyqKxM) | [About U.S. GDP Bar Chart](#us-gdp-bar-chart) |
|     | **Front-End Libraries** |
| [Random Quote Machine](https://codepen.io/badster-pen/full/abBPZXL) | [About Random Quote Machine](#random-quote-machine) |
| [Markdown Previewer](https://codepen.io/badster-pen/full/JjbzoLL) | [About Markdown Previewer](#markdown-previewer) |
| [Drum Machine](https://codepen.io/badster-pen/full/zYoXKXd) | [About Drum Machine](#drum-machine) |
| [Formula Logic Calculator](https://codepen.io/badster-pen/full/abBxgMz) | [About Calculator](#javascript-calculator) |
| [Timer](https://codepen.io/badster-pen/full/YzNKyxB) | [About Timer ](#timer) |
|     | **Responsive Web Design** |
| [Tribute Page](https://codepen.io/badster-pen/full/ExNQgVv) | [About Tribute Page](#tribute-page) |
| [Survey Form](https://codepen.io/badster-pen/full/ExNQMyx) | [About Survey Form](#survey-form) |
| [Product Landing Page](https://codepen.io/badster-pen/full/mdOxryK) | [About Landing Page](#product-landing-page) |
| [Technical Documentation Page](https://codepen.io/badster-pen/full/KKNoeWq) | [About Documentation Page](#technical-documentation-page) |
| [Personal Portfolio](https://codepen.io/badster-pen/full/eYBrpqY) | [About Personal Portfolio](#personal-portfolio) |

</div>

## Data Visualization

### U.S. GDP Bar Chart
   This is a U.S. GDP Bar Chart.

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to U.S. GDP Bar Cart](https://codepen.io/badster-pen/full/jOyqKxM)**

## Front-End Libraries

### Random Quote Machine
   This webpage was made using HTML, SCSS, Flexbox, Bootstrap, and React/Redux. This webapp is made up of one class comoponent with the state handled in Redux. This app made use of two arrays, a quote array and a color array. The quotes used were grabbed from the internet and stored locally in objects made up of two keys - `{ quote: '', author: ''}`. The logic for fetching random quotes was done in the `fetchQuoteAction` function which fetched quotes via index using `Math.floor()`, `Math.random()`, and the length of the quote array. This action function also kept track of the previous index in order to check and prevent immediate repetitive quotes. A similar action creator function was used for fetching the color. I chose to use two reducers for this project, one for quotes and one for the colors. Both were combined using the `combineReducers` function and stored in a root reducer variable that was used to create the store. Inside the main React component, the New Quote button's onClick event calls both the `fetchQuoteAction` and `fetchColorAction` functions to update the component's state. These two action functions are also called in the `componentDidMount` function. I also implemented an animation that fades-in new quotes that are generated. This was done using the `fadeIn` animation from [`react-animations`](https://www.npmjs.com/package/react-animations) and `styled` from [`styled-components`](https://www.npmjs.com/package/styled-components). A button was also implemented to allow users to tweet the generated quote. The twitter icon was used from the [`react-bootstrap-icons`](https://www.npmjs.com/package/react-bootstrap-icons) package.   

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Random Quote Machine](https://codepen.io/badster-pen/full/abBPZXL)**

### Markdown Previewer
   This webapp was made using HTML, SCSS, and React. The app is made up of three class components, `EditorComponent`, `PreviwerComponent`, and `MarkdownPreviewerApp`. The state is handled in the `MarkdownPreviewerApp` component (which acts as the parent component) and is passed down as props to the child components. The `EditorComponent` has a `<textarea>` element with it's value initially set to a default value that's passed into the parent component upon render. The editors `onChange` event is handled in the parent component where it updates the state. The `PreviewerComponent` initially takes in the default value that's passed in, parses and renders it using the [Marked library](https://cdnjs.com/libraries/marked) inside of a `<div>` with the `dangerouslySetInnerHTML` property. Due to the state being handled in the parent component, anytime text is added or deleted in the `EditorComponent` it immediately renders and shows up in the `PreviewerComponent`. 

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Markdown Previewer](https://codepen.io/badster-pen/full/JjbzoLL)**

### Drum Machine
   This webapp was made using HTML, SCSS, Flexbox, and JQuery. The drumpads are `<buttons>` with their associated name in the `id` property and with an `<audio>` tag nested in them. The audio tag has a sound clip from [freewavesamples.com](https://freewavesamples.com) in the `src` property. An `addEventListener` which is set to `keydown` is added to the body of the document and it's loaded in when the document has been rendered. This was done using the `document.ready` function. A switch-case statement is added with the `keyCode` event as the expression. The button associated with the keycode is pressed whenever the key is pressed down using the `$(#id).click()` function. The value of the button which contains the name of the sound that's played is then displayed in the `text-display` div. 

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Drum Machine](https://codepen.io/badster-pen/full/zYoXKXd)**

### Javascript Calculator
   This webapp was made using HTML, SCSS, Flexbox, and React. This calculator functions as a formula logic calculator, meaning it goes through the standard order of operations ([PEMDAS](https://en.wikipedia.org/wiki/Order_of_operations)).The React section of this app is made up of two class components, `CalcButtonsComponent` and `CalculatorApp`. The `CalcButtonsComponent` served as the child of the main `CalculatorApp` component and was used to create the general layout of the calculator. Here a `GridLayout` was created with the [`styled-components`](https://www.npmjs.com/package/styled-components) package. Inside the `GridLayout` a grid was used with a `grid-template-areas` property to map the positions of the buttons via classname. A `calcButton` variable is then created which maps over an array of numpadButtons, this array contained objects with the following properties: `{id: '', buttonName: '', value: '', onClick: '', className: '', backgroundColor: ''}`. All the buttons of the calculator were stored in this format.  Inside the `map()` function, ternary operators were used to check if a background color property was set for the button or if the buttons had an `onClick` property. If a button did have an `onClick` property it would set it to it's correct prop value to keep the operators separate from the number buttons, else it would set both the `onClick` and `backgroundColor` properties to default values (this was namely used for the number buttons). This `map()` function then returned a `<button>` element with the correct properties associated to each object in the numpadButtons array. This `<button>` element is then returned by the component inside the `<GridLayout>` that was created. The parent component would then update the state according to the button that was pressed. Specific functions were created to handle clearing the display, calculating the input, handling number input, handling operator input, and finally handling the decimal input. The state object of this component had the following values: `{inputString: '', result: '', decimalBoolean: false, isNegative: false, evaluated: false}`. Both the result and input were kept in `string` format as it was easier to manipulate and allowed the use of regular-expressions. 

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Javascript Calculator](https://codepen.io/badster-pen/full/abBxgMz)**

### Timer
   This webapp was made using HTML, SCSS, Flexbox, and React. This 25 + 5 Clock/Timer functions as a work/break timer, 25 minutes of work and 5 minutes of break. The React section of this app is made up of three class components, `SessionsComponent`, `TimerComponent`, `ClockApp`, and a stateless functional component, `Session`. The `SessionsComponent` and `TimerComponent` served as children of the main `ClockApp` component and the `Session` component was used to create the Break Length and Session Length elements. This was done due to the fact that both of these elements share a common layout. This component takes in props from the `SessionsComponent` which contains information relating to the Break or Session element as well as onClick properties that increase and decrese the session durations. The `SessionsComponent` returns two Session components, Break Length and Session Length. The `TimerComponent` is used to display the timer and label of the current session, as well as buttons that play, pause and reset the timer. The parent component handles the state of the entire app with the following values: `{timerState: 'stopped', intervalID: '', sessionLength: 25, breakLength: 5, currentSession: 'Session', timer: 1500}`. This main component returns the `TimerComponent`, `SessionsComponent`, and as well as an `<audio>` element that plays an audio clip from [mixkit.co](https://assets.mixkit.co) when the session timer reaches 0:00. The timer itself is handled with the `setINterval()` function, this is stored in the intervalID key in the state object. This is done because it allows a user to start or pause a timer, without having to reset. The timer is formatted into minutes and seconds in the `parseClock()` function, here is where a '0' is prefixed to both mins and seconds when they fall under 10. 

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to 25 + 5 Timer](https://codepen.io/badster-pen/full/YzNKyxB)**

## Responsive Web Design

### Tribute Page
   This tribute page was made using HTML, CSS and Flexbox. The font used in this project is [Playfair Display](https://fonts.googleapis.com/css?family=Playfair+Display) and was imported from the Google Font library using a `<link>` tag. The page itself is formatted using a header and an `<h1>` tag for the title. `<section>` and `<article>` tags are used for the body. The main image is wrapped in an `<a>` tag that links to a Wikipedia page that goes into further detail about the main subject. The image itself contains an `<alt>` tag that follows the best practices for making accessible webpages. Margins, Flexbox's and media queries are used to make the webpage more responsive to different screen sizes. The image itself does resize but does not exceed its original size.

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Tribute Page](https://codepen.io/badster-pen/full/ExNQgVv)**

### Survey Form
  This survey form was created using HTML, CSS, and Flexbox. The font used in this project is [Inconsolata](https://fonts.googleapis.com/css?family=Inconsolata) and was imported from the Google Font Library. This webpage contains an image that's set in the body section of the CSS using the `background-image` property. A small blur filter was applied using the `backdrop-filter` property and the image was set to cover to entire body section. The page is formatted using a `<main>` tag that wraps headers and sections. This webpage was designed as a standard survey form that contains specific questions related to the business. It will not submit unless the required sections are filled correctly. The age input will not accept inputs under 10 and over 100.  

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Survey Form](https://codepen.io/badster-pen/full/ExNQMyx)**

### Product Landing Page
   This webpage was designed and created using HTML, CSS and Flexbox. The fonts used in this project are [Poppins](https://fonts.googleapis.com/css?family=Poppins) and [Lato](https://fonts.googleapis.com/css?family=Lato), both imported from the Google Font Library. This webpage uses a navbar that remains fixed to the top position and resizes and stacks the links when the page changes to a specified size in the CSS. The Get Started section embeds a YouTube video related to the product (in this case Bitcoin) using an `<iframe>` tag that initializes at 640x360. The text in this section uses margins and a block display that's wrapped in a Flexbox to allow for a more responsive page. The next section contains a 1x3 grid with clickable images that link to their specified site. The Markets section contains an embedded widget from [coinlib.io](https://coinlib.io/) which contains information about the current price of Bitcoin.

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Product Page](https://codepen.io/badster-pen/full/mdOxryK)**

### Technical Documentation Page
   This page contains documentation for the Python programming language. I used HTML and CSS to create this webpage. The page contains a navigation section that directs the focus to specific sections in the page. The navigation bar has a fixed position at the left of the page but moves to the top when the window resizes to a width specified in the CSS. 

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Technical Documentation Page](https://codepen.io/badster-pen/full/KKNoeWq)**

### Personal Portfolio
   This webpage utilizes HTML, SCSS, and Flexbox. I decided to use SCSS for this project because I wanted the ability to use variables and `for loops` to help keep my CSS a bit cleaner. I also implemented a [BEM](http://getbem.com/introduction/) style for the CSS to keep the code more organized. The `for loop` was used to iterate through an array of colors and set background color and font color for multiple elements via class. It kept things cleaner and allowed for quick color changes to be made in one swoop. I also utilized `@mixins` for box-shadows which kept the different vendor prefixed properties in one place and used arguments to set them all up, avoiding repetitive code. Media queries were also used to resize font-sizes and the layout of some sections. A grid was utilized to display projects and a small hover animation was used to fill the grid box when hovered. I used another small animation in the Contact section that smoothly moves the text up and changes the color when the cursor hovers over it. This was done using the `transition` property that transformed over the Y-Axis.

**[⬆ Back to Table of Contents](#table-of-contents)**  **[🔗 Link to Personal Portfolio](https://codepen.io/badster-pen/full/eYBrpqY)**

