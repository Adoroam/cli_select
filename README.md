# @utility_belt/cli_select

This package contains a single function used to create a selectable list via the CLI using arrow keys and enter. 

---
## usage
The `default` export "select" is a function that takes 2 arguments. The first is an options object which should contain:

- the question or prompt for the user
- the list of options as an array of strings
- (optional) a color for the currently selected prompt.

### available colors
  - magenta
  - red
  - yellow
  - green 
  - cyan
  - blue

The second argument is a callback function.
The callback function gets passed the currently selected array item as a string.

```Javascript
// example
import cli_select from '@utility_belt/cli_select'

const opts = {
    question: 'how difficult is this to understand?',
    options: [
        'easy',
        'medium',
        'hard'
    ],
    color: 'cyan'
}

const callback = (answer) => {
    console.log('the user has selected: ' + answer)
}

cli_select(opts, callback)

// stdout >> "the user has selected: medium"
```