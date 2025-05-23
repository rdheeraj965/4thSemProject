# 4thSemProject
Main EL for 4th sem

To Run This Project:

Save Files:
- app.py
- Create a folder named templates in the same directory as app.py.
- Inside templates, save client.html and server_dashboard.html.
- Install Libraries:
    pip install Flask Flask-SocketIO python-engineio simple-websocket sympy
- Run Server:
    python app_server.py

Access from Browser/Smartphone:
- Server Dashboard: Open a browser and go to http://your_server_ip:5000/
- Client Page: Open a browser (on your computer or smartphone connected to the same network) and go to http://your_server_ip:5000/client.html (replace your_server_ip with the actual IP address of the machine running the Flask server).

How to Test:

- Open two different browser windows/tabs to http://your_server_ip:5000/client.html. These will represent your two clients.
- Server Password: Enter abc123 (or whatever you set SERVER_PASSWORD to) in the "Server Password" field on both clients and click "Get Equation & Keys".
- The server will generate a polynomial and tell the client the primary and one secondary key (simplified for this demo).
- Client Authentication: Enter a username (e.g., "Alice" for client 1, "Bob" for client 2) and the provided primary/secondary keys in the respective fields. Click "Authenticate with Server".
- Client List: Click "Refresh Client List" on both clients. You should see "Alice" and "Bob" (or whatever usernames you chose) listed.
- File Transfer (Alice to Bob): On Alice's client, enter "Bob's Client ID" (e.g., client_2 or client_1 depending on which client connected first) in the "recipient Client ID" field.
- Click "Choose File" and select any file.
- Click "Request File Transfer".
- On Bob's client, you will see a message: "Incoming file transfer request from Alice (client_1)." and it will show Alice's Primary Key.
- Verification: Bob should visually compare the displayed Primary Key with his own Primary Key (which he entered during authentication). In a real system, this would be a cryptographic check.
- If they match (which they should in this simplified example), Bob clicks "Accept Transfer".
- Alice's client will then start sending file chunks, and Bob's client will receive them and eventually offer a download link.
