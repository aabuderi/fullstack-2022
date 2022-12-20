```mermaid
sequenceDiagram
    participant browser
    participant server
    note over browser: browser sends text of note in POST request
    browser->>server: HTTP POST https://fullstack-exampleapp.herokuapp.com/new_note
    note over server: server saves note from request and returns that browser should reload
    server-->>browser: HTTP status 302
    note over browser: browser reloads page
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->>browser: HTML-code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: main.css
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server-->>browser: main.js

    note over browser: browser starts executing js-code that requests JSON data from server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: [{ content: "HTML is easy", date: "2019-05-23" }, ...]
    
    note over browser: browser executes the event handler that renders notes to display
    ```
