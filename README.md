# Expertkompetens 
## Project report - IoT report template 

### sk in någonstans

The boards that I was concidering were a rasperry pi pico W and a esp32, these boards both have benefits and disadvantages. I choose the rasperry pi pico W since I had this one at home and wanted to start right away, but in afterhand I think that a esp32 maybe would have been a smarter choice. The reaon for this is because I am in big need of as many possibilities as possible to attach moduls, this is something where a esp32 is better at, since this has more pin holes. Another aspect that I would benefit from is because the fact that my system is working pretty rarelly, more specific 2 times a day, depending on the user. This means that it uses energy most of the time without being usefull unless you plug it in every time it will be used. This is of course an option since it placed in my house. But a better idea would be to make it sleep, this is something that can be done using a esp32 but is not possible to achieve using a arduino. 

Apart from this, the rasperry pi pico W has a advantage being a cheeper option, witch is beneficial for scalability. 

**Table of Contents**



# Template


## Tutorial on how to build a smart coocking system [klar]


My name is Max Olsson and I have created a system to make it simple and more fun to coock as it prevents you from making misstakes. The project is a system that allowes you to pick a food from a local website where this then provides you with lighened LED lights that shows what ingridients to pick as well as a button to press when the indredient is picked, to make sure that not only the correct ingredients are picked but also all of them. It also provides you with the recipe and some entertainment while you at it. The time for this project is set to 80h but it highlly depends on how advanced the project is, since it can be very simple and also be extended to a very big project. 

### Objectives [klar]

The purpose of this project was to build something that is relatable to what I do for work but also provide me with something that makes something that I dont like, more enjoyable, in this case coocking. The purpose is to bulletproof coicking. The data can be used for many different purposes, first of all it can give me an insight in what ingredients that I actually use and what are just collecting dust in the storage. But also it is possible to calculate the cost of my meals, automaticlly. Another good benefit is that it can help me with having a good trackreckord of what exists in my storage, and therefore easy know what to buy.

### Material

The basic setup for the IoT device that is created is very small, also it is very easily changible, for example all the buttons can be switched to any sensor that is wanted to be tested. In this project I have chosen to work with the Rasperry Pi Pico W device as seen in Fig. 1, it's a neat little device programmed by MicroPython and has several bands of connectivity. The device has many digital and analog input and outputs and is well suited for an IoT project.



> Example:
>| IoT Thing | For this         |
>| --------- | ---------------- |
>| Rasperry pi pico W |   microcontroller Sizable: 89 kr/st    |
>|  wires|   connect the modules with the rasperry pi Sizable: 29 kr/40st   |
>| mechanical swit hes |  Decition making  Sizable: 36 kr/5st    |
>| LED |  Signal what ingredientsto be picked Sizable: 67kr/300st    |
>| Experiment board |  Help with testing different modules without having to weld  Sizable: 35kr/st   |
>| Resistor | Required for the LED to work resistance Sizable: 68kr/600st   |





### Environment setup. [klar]

The IDE that I have choosen to work with in this project is the Thonny IDE. The reason for this is several, first if using a rasperry pi microprocessor, thonny is preinstalled, this makes it good practice if every wanting to use that. Apart from this, it is very easy to work with files, all that has to be done is upload the file to the mocrocontroller, and then it is possible to make changes directlly in the microcontroller without having to first upload it to the computer. The structure is easy, a main file is used, as well as a .csv file and a JSON file where these keep track on storage and picked ingredients. For using the csv file, no extra library is used, for JSON, the library is already existing in the micropython basic library, therefore no extra instalation is needed. The only required instalation is that when first using the rasperry pi pico W, micropython has to be installed using Thonny. Both the .csv file and the .JSON file can easily be created inside the Thonny IDE, just by simply naming it accordinglly instead of having .py as for a python file. The real installation that was needed to be done apart from installing Thonny, was installing micropython on on the rasperry pi pico W, this was easilly done by pressing the button on the right bottom of the IDE, select the micropython for rasperry pimnpico W and install that on the microcontroller. 


### Putting everything together

When it comes to hardware, I was first deciding between a microcontroller and a microprocessor. A microcontroller having the limiation of only excecute a program send from a computer using a USB port while a microprocessor is a mini computer with a operating system and everything. 

mostlly desiding between a rasperry pi pico W and a 
### Platforms and infrastructure




## Power calculations

This device does not require particulary much power and can since it is always stationed in my kitchen, this results in it having the possibility to either be powered by the local powesupply or by a batterie. Since the system is not placed for example near a vulcano, it is possible to disconnect and connect the the powersupply as it is used or not used. 

When it comes to scalability, the decition to build my own is probably cheaper in prenumerations, but it requires much more work to set up a UI as well as developing different functions. Therefore this is probably better when learniing IoT but not suited for scaling, unless it is a startup company with money limitations. 

## Platforms and infrastructure

The Platform I choose to use is a self made HTML website instead of a existing commersial option. This both since I wanted the freedome to design my own interface but also since I wanted to learn something new and not use already existing solutions. The perks of this is educationl as well as not a cheeper option since no payments is needed to the provider. On the other hand, using a already existing provider can be a better option in many ways, first it requeres less coding, and provides many options that is easily accesable, for example I a way of saving data, this was nothing I had thought of before resulting in me having to create my own solution while the solution from a commersial provider would probably be better and more easily accesable. 



### The code

Import core functions of your code here, and don't forget to explain what you have done. Do not put too much code here, focus on the core functionalities. Have you done a specific function that does a calculation, or are you using clever function for sending data on two networks? Or, are you checking if the value is reasonable etc. Explain what you have done, including the setup of the network, wireless, libraries and all that is needed to understand.

The first thing that was done was to import all the required libraries required for the execution of the code, all of these libraries are already existing within micropython standard libraries. 
```python=
import json
import time
import network
import socket
from machine import Pin

```
Definfing the modules used withing the project
```python=
# Defining the different modules
led_2 = Pin(9, Pin.OUT)
led_chicken = Pin(15, Pin.OUT)
button_1 = Pin(16, Pin.IN, Pin.PULL_UP)
button_2 = Pin(20, Pin.IN, Pin.PULL_UP)
button_3 = Pin(26, Pin.IN, Pin.PULL_UP)

```
Definfing the values used in this project as well as setting their starting values
```python=
# Defining and start values for different variables
balls_on = 0
chicken_on = 0
pancakes_on = 0
done_cocking = 0
Refill_food = 0
knapp_1 = 0
knapp_2 = 0
knapp = 0
knapp_3 = 0
upptagen = 0
with open("affar.json", 'r') as f:
    data = json.load(f)
    chicken_value = str(data[0]['value'])
    pancake_value = str(data[2]['value'])
    meatballs_value = str(data[1]['value'])


ledState = 'led State Unknown'
meatball_knapp = ""
chicken_knapp = ""
pancake_knapp = ""

```
The code snippet below is setting up the WIFI connection as well as informing if the connection failed and provide the correct ip adress that is used to connect to the webpage
```python=
# Home
ssid = 'XXXXX'
password = 'XXXXXX'


wlan = network.WLAN(network.STA_IF)
wlan.active(True)
wlan.connect(ssid, password)

# Wait for connect or fail
max_wait = 10
while max_wait > 0:
    if wlan.status() < 0 or wlan.status() >= 3:
        break
    max_wait -= 1
    print('waiting for connection...')
    time.sleep(1)
    
# Handle connection error
if wlan.status() != 3:
    raise RuntimeError('network connection failed')
else:
    print('Connected')
    status = wlan.ifconfig()
    print( 'Local server ip = ' + status[0]+":83" )
    
    
# Open socket
addr = socket.getaddrinfo('0.0.0.0', 83)[0][-1]
s = socket.socket()
s.bind(addr)
s.listen(1)
print('listening on', addr)
```
The function below is created to constantlly check the buttons and and register if they are pressed for longer than 0,1 seconds. This since otherwise a button might be pressed while noone is updating the code and therefore the buttonp press might not be noticed.
```python=
import _thread as thread
import time

def check_buttons(): # checking for buttun
    global knapp_1  #global value
    global knapp_2  #Global value
    global knapp
    global knapp_1_resultat
    global knapp_3
    while True: # snurra för alltid
        #Check if buttons are pressed (every 0.1s) here and update their values
        #print(" knappen:" , button_1.value())
        time.sleep(0.1)
        if (button_1.value() == 0 ):
            knapp = 1
        if (button_2.value() == 0 ):
            knapp_2 = 1
        #if (button_3.value() == 0 ):
         #   knapp_3 = 1
        if (knapp == 1) and (knapp_2 == 1):# and (knapp_3 == 1):
            knapp_1 = 1
            
        #print(button_2.value())

thread.start_new_thread(check_buttons,())
```
In the code below, a request from the cliend is accepted and the HTTP string is broken down to only include the part of the string that contains information that isusefull. 
```python=
        cl, addr = s.accept()
        print('client connected from', addr)
        request = cl.recv(1024)
        print("request:")
        print(request)
        request = str(request)
        start = request.find("GET /?")
        end = request.find(" HTTP/1.1")

        request = request[start:end]
```
In this code, the .JSON file is opened, the value is changed, in this case the number of meatballs in the storage is decreased with 1, and the .JSON file is then updated accordinglly.
```python=
            with open("affar.json", 'r') as f:
                data = json.load(f)
                data[1]['value'] -= 1
                meatballs_value = str(data[1]['value'])
            with open("affar.json", 'w') as f:
                json.dump(data, f)
```
In this code below, the .csv file is opened and "Meatballs" is appanded to the list of ingredients that has ben used since the start of the use of this IoT devide.
```python=
            file=open("storage.csv","a")
            file.write(',Meatballs')
            file.close()
```
In the section below, the HTML code is created and witch is what is seen in the webside.
```python=
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="icon" href="data:,">
    <style>
        html {
            font-family: Helvetica;
            display: inline-block;
            margin: 0px auto;
            text-align: center;
        }

        .buttonone {
            background-color: #4CAF50;
            border: 2px solid #000000;
            ;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }

        .buttondos {
            background-color: #4CAF50;
            border: 2px solid #000000;
            ;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }

        .buttontres {
            background-color: #4CAF50;
            border: 2px solid #000000;
            ;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }

        .buttontfour {
            background-color: #4CAF50;
            border: 2px solid #000000;
            ;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }


    </style>
</head>

<body>
    <center>
        <h1>Choose your meal</h1>
    </center><br><br>
    <form>
        <center>
            <center> <button class="buttonone" name="balls" value="on" type="submit"> Meatballs on</button>
                <br><br>
                <center> <button class="buttondos" name="pancakes" value="on" type="submit">Pancakes on</button>
    </form>
    <br><br>
    <center> <button class="buttontres" name="chicken" value="on" type="submit">Chicken on</button>
        </form>
        <br><br>
        <center> <button class="buttontfour" name="Done" value="on" type="submit">Done cocking</button>
            </form>
            <br><br>
        <center> <button class="buttontfour" name="Fill" value="on" type="submit">Fill storage</button>
            </form>
            <br><br>
            <br><br>
            <p>%s
            <p>
</body>
<iframe width="420" height="315"
src="https://www.youtube.com/embed/tgbNymZ7vqY">
</iframe>

</html>
"""
```
In the code below, after the request is send from the client to the server and has been processed and executed, the respons is now sent back to the cliend in the code snipped below.
```python=
        response = html % stateis
        cl.send('HTTP/1.0 200 OK\r\nContent-type: text/html\r\n\r\n')
        cl.send(response)
        cl.close()
```
In the code snippet below, the LED light "led_2" is lightened.
```python=
            led_2.value(1)
```



### The physical network layer


The wireless protocol that I used in this project is the WiFi protocol and the transport protocol is the HTTP protocol where the data is sent every time a operator initiates a HTTP request crom the webpage.

The process of this IoT device is that the first thing is that the operator is pressing a button on a screen, this is the client, this then sends a HTTP request to the HTTP server, in this case the rasperry pi pico W. The HTTP server then receives the request, takes action accordinglly, for example lighting a LED light and checking the button statuses, then the HTTP server sends a HTTP respons back to the HTTP client. The HTTP cliend receives this respons and shows the respons on the HTTP webpage. 

The data is only sent to the webpage as a command is requested from the operator, for example a request to get pickorder for a certain meal. The wireless protocol used in this project is WIFI as the transport protocol is HTTP requests sent using sockets. The decition of using WIFI is that first of all the range is not really a problem since the operator will never be further away than 3 meter from the kitchen. Also it is a easy way of giving axcess to everyone that has acess to the WIFI, also since this is setup in my home, there is no security problems when sendiing this using WIFI. Also I wanted to avoid extra material, therefore the LoRa would not be the best fit for me. Also using a LoRa, this puts more limitation on what can be sent, this is avoided using WIFI. Another benefit with using WiFi over LoRa is since it is less energy demanding, therefore if not needed, this is not really a option. In conclusion, my choise of WiFi over LoRa was based on possibility to send more data and easy access in return of shorter range and lower power consumption.

## missing

Why did I use HTTP request and not webhook etc


### Visualisation and user interface

The data is sent only to the webpage as the a request/trigger from the operator is sent by pressing a button. When it comes to storing data, this is done with .csv and .JSON files. The .csv and .JSON file, data is sent to them only when it is needed, for example when picking a ingridient, this sends data to the .JSON and .csv files. The reasonging why I decided to use .JSON for storage, is because it is a easy way to use dictionary and to change values in this dictionary while a .csv file is used fore providing a list of picked ingredients, this since it provides a very simple way of appending a string to a existing list.





### Finalizing the design

Show the final results of your project. Give your final thoughts on how you think the project went. What could have been done in an other way, or even better? Pictures are nice!

- [ ] Show final results of the project
- [ ] Pictures
- [ ] *Video presentation

---
