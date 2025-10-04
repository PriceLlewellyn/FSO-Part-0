sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Enter https://studies.cs.helsinki.fi/exampleapp/spa
    browser->>user: GET /spa
    activate server
    server->>browser: HTML docuemnt
    deactivate server

    browser->>server: GET /main.css
    activate server
    server->>browser: CSS file
    deactivate srever

    browser->>server: GET /spa.js
    activate server
    server->>browser: JavaScript file
    deactivate server

    Note right of browser: Browser executes spa.js

    browser->>server: GET /data.json
    activate server
    server->>browser: JSON data with notes
    deactivate server

    Note right of browser: Browser renders notes dynamically into the page