# Expertkompetens 
## Project report - IoT report template 



**Table of Contents**



# Template


## Tutorial on how to build a smart coocking system


My name is Max Olsson and I have created a system to make it simple and more fun to coock as it prevents you from making misstakes. The project is a system that allowes you to pick a food from a local website where this then provides you with lighened LED lights that shows what ingridients to pick as well as a button to press when the indredient is picked, to make sure that not only the correct ingredients are picked but also all of them. It also provides you with the recipe and some entertainment while you at it. The time for this project is set to 80h but it highlly depends on how advanced the project is, since it can be very simple and also be extended to a very big project. 

### Objectives

The purpose of this project was to build something that is relatable to what I do for work but also provide me with something that makes something that I dont like, more enjoyable, in this case coocking. The purpose is to bulletproof coicking. The data can be used for many different purposes, first of all it can give me an insight in what ingredients that I actually use and what are just collecting dust in the storage. But also it is possible to calculate the cost of my meals, automaticlly. Another good benefit is that it can help me with having a good trackreckord of what exists in my storage, and therefore easy know what to buy.

### Material

Explain all material that is needed. All sensors, where you bought them and their specifications. Please also provide pictures of what you have bought and what you are using.

- [ ] List of material
- [ ] What the different things (sensors, wires, controllers) do - short specifications
- [ ] Where you bought them and how much they cost


> Example:
>| IoT Thing | For this         |
>| --------- | ---------------- |
>| Perhaps   | a table          |
>| is a      | jolly good idea? |
>
>In this project I have chosen to work with the Rasperry Pi Pico W device as seen in Fig. 1, it's a neat little device programmed by MicroPython and has several bands of connectivity. The device has many digital and analog input and outputs and is well suited for an IoT project.


### Environment setup

The IDE that I have choosen to work with in this project is the Thonny IDE. The reason for this is several, first if using a rasperry pi microprocessor, thonny is preinstalled, this makes it good practice if every wanting to use that. Apart from this, it is very easy to work with files, all that has to be done is upload the file to the mocrocontroller, and then it is possible to make changes directlly in the microcontroller without having to first upload it to the computer. The structure is easy, a main file is used, as well as a .csv file and a JSON file where these keep track on storage and picked ingredients. For using the csv file, no extra library is used, for JSON, the library is already existing in the micropython basic library, therefore no extra instalation is needed. The only required instalation is that when first using the rasperry pi pico W, micropython has to be installer using Thonny.


### Putting everything together

When it comes to hardware, I was first deciding between a microcontroller and a microprocessor. A microcontroller having the limiation of only excecute a program send from a computer using a USB port while a microprocessor is a mini computer with a operating system and everything. 

mostlly desiding between a rasperry pi pico W and a 
### Platforms and infrastructure

The Platform I choose to use is a self made HTML website instead of a existing commersial option. This both since I wanted the freedome to design my own interface but also since I wanted to learn something new and not use already existing solutions. The perks of this is educationl as well as not a cheeper option since no payments is needed to the provider. On the other hand, using a already existing provider can be a better option in many ways, first it requeres less coding, and provides many options that is easily accesable, for example I a way of saving data, this was nothing I had thought of before resulting in me having to create my own solution while the solution from a commersial provider would probably be better and more easily accesable. 

When it comes to scalability, the decition to build my own is probably cheaper in prenumerations, but it requires much more work to set up a UI as well as developing different functions. Therefore this is probably better when learniing IoT but not suited for scaling, unless it is a startup company with money limitations. 

### The code

Import core functions of your code here, and don't forget to explain what you have done. Do not put too much code here, focus on the core functionalities. Have you done a specific function that does a calculation, or are you using clever function for sending data on two networks? Or, are you checking if the value is reasonable etc. Explain what you have done, including the setup of the network, wireless, libraries and all that is needed to understand.


```python=
import this as that
def my_cool_function():
    print('not much here')
s.send(package)
# Explain your code!
```

### The physical network layer


The process of this IoT device is that the first thing is that the operator is pressing a button on a screen, this is the client, this then sends a HTTP request to the HTTP server, in this case the rasperry pi pico W. The HTTP server then receives the request, takes action accordinglly, for example lighting a LED light and checking the button statuses, then the HTTP server sends a HTTP respons back to the HTTP client. The HTTP cliend receives this respons and shows the respons on the HTTP webpage. 

The data is only sent to the webpage as a command is requested from the operator, for example a request to get pickorder for a certain meal. The wireless protocol used in this project is WIFI as the transport protocol is HTTP requests sent using sockets. The decition of using WIFI is that first of all the range is not really a problem since the operator will never be further away than 3 meter from the kitchen. Also it is a easy way of giving axcess to everyone that has acess to the WIFI, also since this is setup in my home, there is no security problems when sendiing this using WIFI. Also I wanted to avoid extra material, therefore the LoRa would not be the best fit for me. Also using a LoRa, this puts more limitation on what can be sent, this is avoided using WIFI.


### Visualisation and user interface

The data is sent only to the webpage as the a request/trigger from the operator is sent by pressing a button. When it comes to storing data, this is done with .csv and .JSON files. The .csv and .JSON file, data is sent to them only when it is needed, for example when picking a ingridient, this sends data to the .JSON and .csv files. The reasonging why I decided to use .JSON for storage, is because it is a easy way to use dictionary and to change values in this dictionary while a .csv file is used fore providing a list of picked ingredients, this since it provides a very simple way of appending a string to a existing list.



### Finalizing the design

Show the final results of your project. Give your final thoughts on how you think the project went. What could have been done in an other way, or even better? Pictures are nice!

- [ ] Show final results of the project
- [ ] Pictures
- [ ] *Video presentation

---
