sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Type note and cick save
    Note to right of browser: Javascript captures input

    browser->>browser: Add new note to page (DOM updated)

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa (note data in JSON)
    activate server
    server->>browser: Response 201 Created (note saved)
    deactivate server

    Note right of browser: The SPA stays on the same page, updated notes are already visible



    