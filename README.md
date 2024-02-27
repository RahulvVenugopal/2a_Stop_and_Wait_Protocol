# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```import time
class StopAndWaitProtocol:
    def __init__(self):
        self.timeout = 1

    def send(self, frame):
        print("Sending frame:", frame)
        time.sleep(0.5)
        ack_received = False
        start_time = time.time()

        while not ack_received:
            if time.time() - start_time >= self.timeout:
                print("Timeout! Resending frame:", frame)
                start_time = time.time()
            else:
                ack_received = self.receive_ack(frame)

    def receive_ack(self, frame):
        received = input("Enter '1' to simulate successful acknowledgment, '0' for failure: ")
        return received == '1'

if __name__ == "__main__":
    protocol = StopAndWaitProtocol()
    frames_to_send = ['Frame1', 'Frame2', 'Frame3']
    
    for frame in frames_to_send:
        protocol.send(frame)
```
## OUTPUT
![Screenshot (139)](https://github.com/RahulvVenugopal/2a_Stop_and_Wait_Protocol/assets/144132514/6a8d8bf3-1fbe-45bb-9d32-b1d3252e0df3)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
