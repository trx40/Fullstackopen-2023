# 0.6 New note in Single page app diagram

## Diagram using the mermaid markdown syntax to depict the sequence of events where the user creates a new note using the single-page version of the app.

```mermaid
sequenceDiagram
    participant browser
    participant server

    
    Note over browser: The JS code on browser intercepts the form submission<br /> and pushes the note object into the note array

    Note over browser: Execute redrawNotes() notes function to render the latest notes

    Note right of browser: Execute sendToServer() which sends this note to the server<br /> as a POST request

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: message: note created
    deactivate server
```