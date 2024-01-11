Display Player Names
======================
In this activity, you will display the player names on the game board based as players join the game server.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10927666/Screenshot_2023-11-17_at_9.43.12_AM.png" width = "100%" height = "50%">




Follow the given steps to complete this activity.




1. Create a global list “player_names” and append the player name to the list as they join the server.


* Open the file “server.py”.
* Create a global list "player_names" to store the names of the players.
```
player_names = []
```


* Access the player_names globally inside the handle_client() method. Append the player name to the global player list when a player joins the game. 
```
global CLIENTS, player_names
player_names.append({"name": player_name, "type": CLIENTS[player_name]["player_type"]})
time.sleep(2)


```
* Send the global player list to all the clients using the socket.send() method.
```
 for client in CLIENTS:
     c_socket = CLIENTS[client]["player_socket"]
     c_socket.send(str({"player_names" : player_names}).encode())


```
2. Display the player names in the two labels created on the game canvas.


* Open the file `client.py`.
* Check if the message has the string "player_names" in it. Fetch and store player names in a list.
```
if('player_names' in message):
    players = eval(message)                   
    players_names = players["player_names"]
```


* Update the player names on the game canvas based on the player type. 
```
for player in players_names:
    if(player["type"] == 'player1' and canvas2):
       canvas2.itemconfigure(player1_label, text="Player1: " + player['name'])
       
     if(player['type'] == 'player2' and canvas2):
        canvas2.itemconfigure(player2_label, text="Player2: " + player['name'])




```


* Save and run the code by first running the server.py and then twice client.py to check the output.
