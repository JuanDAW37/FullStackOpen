        A[User] --> browser{writes a note in a input box}
        A[User] --> browser{Strokes the Save button}
        browser --> server: POST https://exampleapp/new_note

        activate server
        server-->browser: 201 Created
        server-->browser: redirect to https://studies.cs.helsinki.fi/exampleapp/notes
        deactivate server

        browser-->server: GET https://studies.cs.helsinki.fi/exampleapp/notes
        activate server
        server-->browser: HTML code
        deactivate server

        browser-->server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server-->browser: CSS code
        deactivate server

        browser-->server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
        activate server
        server-->browser: JS code
        deactivate server

        Annotation from the browser: data is requested from the browser from the server

        browser-->server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
        activate server
        server-->browser: [{ "content": "data example", "date": "2024/07/21" }, ... ]
        deactivate server

        Annotation from the browser: browser executes the callback function that renders the data
