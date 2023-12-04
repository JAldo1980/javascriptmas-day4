# javascriptmas-day4
A simple API request application built with JavaScript

This challenge was part of a 24 day JavaScript challenge - great to tidy up and improve my exisiting JavaScript skills.
(link to my original post here: https://twitter.com/_JamesCodes/status/1731645168858575270)

<h3>Here's the final product below:</h3>

![family-guy](https://github.com/JAldo1980/javascriptmas-day4/assets/80925002/b416aa5c-7aa9-4c08-8334-64dbe611b998)

## Technologies Used

- **HTML5:** The structure of the web page is created using HTML5.
- **CSS3:** Styling and animations for the door opening and joke display are implemented using CSS3.
- **JavaScript:** The interactivity of the application is powered by JavaScript.
- **Fetch API:** Utilized the Fetch API to asynchronously retrieve a random dad joke in JSON format from [icanhazdadjoke](https://icanhazdadjoke.com/).
- **Audio API:** Used the Web Audio API to play a laughter sound effect when the window is clicked.

## Code Details

### Opening the Door and Displaying a Joke

```javascript
document
  .getElementById("window-container")
  .addEventListener("click", function () {
    // ... (Audio setup, door animations)

    // Fetch a random dad joke as JSON
    fetch("https://icanhazdadjoke.com/", {
      headers: {
        Accept: "application/json",
      },
    })
      .then((response) => response.json())
      .then((data) => {
        // Display the joke
        document.getElementById("joke-display").innerHTML = `
          <p>${data.joke}</p>
        `;
      })
      .catch((error) => {
        console.error("Error fetching dad joke:", error);
      });

    // ... (More animations)
  });

### Closing the door 

const closeDoor = document.getElementById("close-door");

closeDoor.addEventListener("click", closeDoorFunction);

function closeDoorFunction() {
  // ... (Door closing animations)
}
