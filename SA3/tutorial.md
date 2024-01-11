Display the Winner
======================
In this activity, you will display the winning message when a player wins the game.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10927636/sa3updated.gif" width = "100%" height = "50%">




Follow the given steps to complete this activity.


1. Display the winning message on the game canvas.
* Open the file “client.py”.
* Add a new label to the canvas to display the winning text.
```
wining_message= None
global wining_message
wining_message = canvas2.create_text(screen_width/2 + 10, screen_height/2 + 250, text = "", font=("Chalkboard SE",font_size), fill='#fff176')
```


* Define the handle_win() method to display the winning message label with the winning text.
```
def handle_win(message):
    global wining_message
    if 'Player1' in message:
        color = 'red'
    else:
        color = 'yellow'
   canvas2.itemconfigure(wining_message, text = message, fill = color)
```


* Call the handle_win() method inside received_msg() if the winning message is received from the server.
```
if('wins the game.' in message):
     handle_win(message)
```


* Send the greeting message to the clients connected to the server when a player reaches home.
```
if(color=='red'):
   greet_message = 'Player1 wins the game.'
else:
   greet_message = 'Player2 wins the game.'
SERVER.send(greet_message.encode())
```
* Save and run the code by first running the server.py and then client.py to check the output.
