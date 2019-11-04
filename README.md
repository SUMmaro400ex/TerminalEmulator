# Terminal Emulator WebComponent
![Example](example.gif)

## How It Works
The `index.js` file inserts into the `window` a function called `insertTerminalEmulator`. Use this function to provide the `querySelector` for where the emulator should be inserted, and the array of commands you would like to have the terminal mock execution for. Each command consists of three parts, `path`, `input`, and `results`. The `path` is what will be shown as the current path, the `input` is the mock terminal `input` and the `results`, is what the execution of the `input` returns. Note that `results` can be an empty array for commands like `cd`. 
```js       
    const terminalLines = [
            {
                path: '~/Jon/Skills',
                input: 'ls',
                results: ['React', 'JavaScript', 'GraphQL', 'Node', 'HTML', 'CSS', 'SCSS', 'Web-Components', 'Ruby', 'Swift', 'SwiftUI'],
            }
        ];
     document.addEventListener('DOMContentLoaded', () => window.insertTerminalEmulator({ querySelector: '#terminal', terminalLines, disableFontInsertion: false }));
```

## Important Notes
- The terminal will add scroll bars if the content gets too tall and will automatically scroll to the bottom
- The font the terminal uses is `Inconsolata`. The terminal emulator will insert a link to the Google Font for you. If you already have this font, you can disable the auto insertion of the font by sending disableFontInsertion as `true`.

## Whats Next
Eventually this will be bundled up into an npm package. Usage will work the exact same, except `insertTerminalEmulator` function will be exported instead of being inserted into the `window`