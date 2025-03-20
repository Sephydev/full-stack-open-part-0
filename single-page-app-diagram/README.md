# Single Page App Diagram

This is a simple diagram representing what's going on when a user goes to https://studies.cs.helsinki.fi/exampleapp/spa using the Mermaid syntax:

```mermaid
sequenceDiagram
  participant browser
  participant server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
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

  Note on right of the browser: the browser execute the JS script who fetches the JSON file

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->>browser: the JSON file
  deactivate server
```