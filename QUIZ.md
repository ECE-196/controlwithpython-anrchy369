### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?
the board uses the on_event when getting a serial message. it checks to see if it is valid for the LED status. Will send an OK byte if good or ERR byte if bad.
naive is under a constant loop for incoming messages. the other method needs to be triggered.
### What does `detached_callback` do? What would happen if it wasn't used?
it is an asynchrounos function when runs in parallel to the main.
delays could happen and the UI would stall and freeze up.
### What does `LockedSerial` do? Why is it _necessary_?
ensures that messages go one at a time at the serial port.
ensures data does not get cross contaminated and corrupt.
