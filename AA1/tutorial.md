Add Players' Scores
======================
In this activity, you will add two new labels to display the players' scores on the game canvas.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10927635/aa1new.gif" width = "100%" height = "50%">




Follow the given steps to complete this activity.




1. Create two new labels for displaying the players’ scores.
* Open the file “client.py”.
* Create two variables player1_score_label and player2_score_label, set them to None.
```
player1_score_label = None
player2_score_label = None
```
* Create two variables to store the score of each player player1_score and player2_score and set them to 0.
```
player1_score=0
player2_score=0
```


* Access the two variables globally. Create two labels with the default value “0” and store them in the two variables player1_score_label and player2_score_label inside the game() method.
```
global player1_score_label, player2_score_label


player1_score_label = canvas2.create_text(screen_width * 0.25, screen_height * 0.25, text = "0", font=("Chalkboard SE",font_size), fill='#fff176' )
    player2_score_label = canvas2.create_text(screen_width * 0.75, screen_height * 0.25, text = "0", font=("Chalkboard SE",font_size), fill='#fff176' )
```


2. Display the players’ scores on the label.
* Define a new function update_score() to update the score and the label text of the players.
```
def update_score(message):
    global canvas2, player1_score, player2_score, player1_score_label, player2_score_label
    if('Player1' in message):
        player1_score +=1
    else:
        player2_score +=1


    canvas2.itemconfigure(player1_score_label, text = player1_score)
    canvas2.itemconfigure(player2_score_label, text = player2_score)
    print(player1_score,  player2_score)


```
* Create a new global variable flag to check the win state of the game and set it to false. Access it globally inside the received_msg() method. 
```
is_win_state = False


global is_win_state
```


* Also, check if is_win_state is False while checking for the winning message. If true, call the update_score() function with the winning message and set is_win_state to true.
```
if('wins the game.' in message and is_win_state == False):
     handle_win(message)
     update_score(message)
     is_win_state = True


```
* Save and run the code by first running the server.py and then client.py to check the output.
