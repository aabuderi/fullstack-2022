```mermaid
sequenceDiagram
    participant browser
    participant server

    note over browser: Browser redraws notes list
    note over browser, server: browser sends note as a JSON message
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    
    note over server: server decodes JSON and saves note
    server-->>browser: Response 201 Created
```
