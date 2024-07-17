# sequenceDiagram

participant User
participant Browser
participant Server

User->>Browser: Enter note in text field
User->>Browser: Click "Save" button
Browser->>+Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
Server-->>Browser: HTTP 302 (URL redirect)
Browser->>+Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
Server-->>+Browser: HTML document
Browser->>-Server: GET <https://studies.cs.helsinki.fi/exampleapp/main.css>
Server-->>Browser: main.css
Browser->>Server: GET <https://studies.cs.helsinki.fi/exampleapp/main.js>
Server-->>+Browser: main.js
Browser->>-Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
Server-->>+Browser: data.json (including the new note)
Browser->>-User: Display updated notes page
