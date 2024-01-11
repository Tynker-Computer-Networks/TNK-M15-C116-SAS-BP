Add the Reset Button
======================
In this activity, you will add a button to restart the game after a player wins the game.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10929562/image__54_.png" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Reset the color of the boxes
* Open the file `client.py`.
* Loop through the right boxes and set the background of each box to white.  
```
for rBox in right_boxes:
      rBox.configure(bg='white')
```
* Loop through the left_boxes and set background of each box to white
```
for lBox in left_boxes:
      lBox.configure(bg='white')
```


* Set the color of the first box on the left and right to red and yellow respectively. Set the color of the finishing_box to green.
```
left_boxes[0].configure(bg='red')
right_boxes[0].configure(bg='yellow')
finishing_box.configure(bg='green')
```
2. Update the winning message and win_state of the game.
* Set winning_message to "" and destroy the reset button.
```
canvas2.itemconfigure(wining_message, text="")
reset_button.destroy()
```


* Recreate the Reset button for the next game and Set is_win_state to False 
```
reset_button =  Button(game_window,text="Reset Game", fg='black', font=("Chalkboard SE", int(font_size * 0.5)), bg="grey",command=reset_game, width=10, height=1)


is_win_state = False
```


* Save and run the code by first running the server.py and then client.py to check the output.
