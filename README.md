````markdown
# Voting System

A simple voting system implemented using JavaScript with `Map` and `Set` data structures. This system allows creating polls with multiple options, prevents duplicate votes per voter per option, and displays poll results.

---

## Features

- Create a poll with multiple unique options.
- Prevent adding empty or duplicate options.
- Allow users to vote for options using unique voter IDs.
- Prevent duplicate votes by the same voter on the same option.
- Display current poll results with vote counts per option.

---

## Installation

No special installation is required. This project uses plain JavaScript and can run in any modern JavaScript environment (Node.js or browser console).

---

## Usage

1. **Initialize poll**

```js
const poll = new Map();
```

2. **Add options**

```js
addOption("Turkey");   // returns: Option "Turkey" added to the poll.
addOption("Morocco");  // returns: Option "Morocco" added to the poll.
addOption("Egypt");    // returns: Option "Egypt" added to the poll.
```

3. **Cast votes**

```js
vote("Turkey", "traveler1");  // returns: Voter traveler1 voted for "Turkey".
vote("Turkey", "traveler2");  // returns: Voter traveler2 voted for "Turkey".
vote("Morocco", "traveler3"); // returns: Voter traveler3 voted for "Morocco".
```

4. **Display results**

```js
console.log(displayResults());
/* Output:
Poll Results:
Turkey: 2 votes
Morocco: 1 votes
Egypt: 0 votes
*/
```

---

## API

### `addOption(option)`

* Adds a new option to the poll.
* **Parameters:** `option` (string) - the option to add.
* **Returns:**

  * `"Option "<option>" added to the poll."` if successfully added.
  * `"Option cannot be empty."` if the option is empty.
  * `"Option "<option>" already exists."` if the option is already in the poll.

### `vote(option, voterId)`

* Registers a vote for an option by a unique voter.
* **Parameters:**

  * `option` (string) - the voting option.
  * `voterId` (string) - unique identifier for the voter.
* **Returns:**

  * `"Voter <voterId> voted for "<option>"."` on successful vote.
  * `"Voter <voterId> has already voted for "<option>"."` if duplicate vote.
  * `"Option "<option>" does not exist."` if the option does not exist.

### `displayResults()`

* Returns a formatted string of all poll options and their vote counts.

---

## Data Structures

* Uses a `Map` where keys are poll options and values are `Set`s of voter IDs.
* The `Set` prevents duplicate votes by the same voter for an option.

---

## Testing

Ensure you have at least three options and three votes to meet lab requirements. Use the provided functions to simulate voting and view results.

---

## License

This project is provided as-is for educational purposes.

---

## Author

Developed by \Jordan Leturgez
