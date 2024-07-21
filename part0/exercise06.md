        A[User] --> browser{writes a note in a input box}
        A[User] --> browser{Strokes the Save button}
        browser --> server: POST [text](https://studies.cs.helsinki.fi/exampleapp/new_note_spa)        
        activate server
        server-->browser: 201 Created
        deactivate server