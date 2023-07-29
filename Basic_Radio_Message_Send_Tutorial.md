# Basic Radio Message Send Tutorial

## Step 1 
### First, we need to set up the radio group number for both micro: bits to communicate on the same channel.

Drag and drop ``|| radio: radio setgroup 1 ||`` in the ``|| basic: on start ||`` block. This is found in the ``||Radio:||`` Section

This set the radio group to 1, however you may need to change the number if other
people in class are using the same radio group.

You will also want to delete the ``|| basic: Forever ||`` block.We don't need it for this project
and having a clean workspace is important. 

```blocks
radio.setGroup(1)
```


## Step 2 Sending Messages
### In the next two steps we'll make the microbit send messages when we press the A or B button

Drag and drop the ``|| input: on button A pressed ||`` block from the ``|| Input:||`` section into the workspace.

Place the ``|| radio: radio send string ||`` block from the ``|| Radio:||`` section inside the ``|| input: on button A pressed ||`` block.

Type "YES" into the ``|| radio: radio send string ||`` block.

This block sends the message "YES" when button A is pressed.



```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("YES")
})
```

## Step 3 Sending Messages Part 2
### We will repeat the same steps for Step 2, but now for the B button Block

Now, drag and drop the ``|| input: on button B pressed ||`` block from the ``|| Input:||`` section into the workspace.

Inside the ``|| input: on button B pressed ||`` block, add the ``|| radio: radio send string ||`` block.

Type "NO" into the ``|| radio: radio send string ||`` block.

This block sends the message "NO" when button B is pressed.



```blocks
input.onButtonPressed(Button.B, function () {
    radio.sendString("NO")
})
```

## Step 4 Receiving Messages
### In this step, we'll code the second micro:bit to receive and display the messages sent by the first micro:bit.

Drag and drop the ``|| radio: on received string ||`` block from the ``|| Radio:||`` section into the workspace.

Inside the ``|| radio: on received string ||`` block, add the ``|| basic: show string ||`` block from the ``|| Basic:||`` section.

This block is triggered whenever a message is received.It will display the received message on the LED screen

    ```blocks
radio.onReceivedString(function (receivedString) {
    basic.showString(receivedString)
})
```

## Step 5 Download and Test code

Download the code to your two microbits! 
When you press Button A on on microbit, it should send YES to the other one.
When you press Button B on the microbit, it should send NO to the other one.