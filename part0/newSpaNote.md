
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET: https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: the HTML document
    deactivate server

    browser->>server: GET: https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET: https://studies.cs.helsinki.fi/exampleapp/spa.js 
    activate server
    server-->>browser: the Javascript file
    deactivate server

    browser->>server: GET: https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content":"test","date":"2023-02-28T12:02:18.546Z"}, ...}]
    deactivate server

Note right of browser: The browser executes the callback function that renders the notes 

    browser->>server: POST: https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: 
    deactivate server

