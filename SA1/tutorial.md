Add Player Name Labels
======================
In this activity, you will add two labels on the game canvas.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10927634/sa1img.png" width = "100%" height = "50%">




Follow the given steps to complete this activity.




1.Declare two variables for the two labels.
* Open the file “client.py”.
* Create two variables for two different players and initialize them with value “None”.
```
player1_label = None
player2_label = None
```


* Access the two variables globally inside the game() method. Create two text labels on the canvas and store them in the two variables created above.
```
global player1_label, player2_label
player1_label = canvas2.create_text(screen_width * 0.25, screen_height * 0.5, text = "Player1: Joining", font=("Chalkboard SE",font_size), fill='red')
   
player2_label = canvas2.create_text(screen_width * 0.75, screen_height * 0.5, text = "Player2: Joining", font=("Chalkboard SE",font_size), fill='yellow')
```


* Save and run the code by first running the server.py and then client.py to check the output.
