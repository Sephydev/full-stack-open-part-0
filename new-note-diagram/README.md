# New Note Diagram

Here is a simple sequence diagram representing what is going on when a user goes to https://studies.cs/helsinki.fi/exampleapp/notes, using the Mermaid syntax:

```mermaid
sequenceDiagram
  participant browser
  participent server

  browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
  activate server
  server-->>browser: Ask the user to go to https://studies.cs.helsinki.fi/exampleapp/notes
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server-->>browser: the HTML document
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server-->>browser: the CSS stylesheet
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server-->>browser: the JS script
  deactivate server

  Note on the right of browser: The browser start reading the JS script who fetches the JSON document

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->>browser: the JSON file
  deactivate server
```