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

How is all the electronics connected? Describe all the wiring, good if you can show a circuit diagram. Be specific on how to connect everything, and what to think of in terms of resistors, current and voltage. Is this only for a development setup or could it be used in production?

- [ ] Circuit diagram (can be hand drawn)
- [ ] Electrical calculations
- [ ] Limitations of hardware depending on design choices.
- [ ] Discussion about a way forward - is it possible to scale?

### Platforms and infrastructure

Describe your choice of platform(s). You need to describe how the IoT-platform works, and also the reasoning and motivation about your choices. Have you developed your own platform, or used 

Is your platform based on a local installation or a cloud? Do you plan to use a paid subscription or a free? Describe the different alternatives on going forward if you want to scale your idea.

- [ ] Describe platform in terms of functionality
- [ ] Explain and elaborate what made you choose this platform
- [ ] Provide a pricing discussion. What are the prices for different platforms, and what are the pros and cons of using a low-code platform vs. developing yourself?

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

How is the data transmitted to the internet or local server? Describe the package format. All the different steps that are needed in getting the data to your end-point. Explain both the code and choice of wireless protocols.

- [ ] How often is the data sent? 
- [ ] Which wireless protocols did you use (WiFi, LoRa, etc ...)?
- [ ] Which transport protocols were used (MQTT, webhook, etc ...)
- [ ] Elaborate on the design choices regarding data transmission and wireless protocols. That is how your choices affect the device range and battery consumption.
- [ ] What alternatives did you evaluate?
- [ ] What are the design limitations of your choices?

### Visualisation and user interface

Describe the presentation part. How is the dashboard built? How long is the data preserved in the database?

- [ ] Provide visual examples on how the visualisation/UI looks. Pictures are needed.
- [ ] How often is data saved in the database. What are the design choices?
- [ ] Explain your choice of database. What kind of database. Motivate.
- [ ] Automation/triggers of the data.
- [ ] Alerting services. Are any used, what are the options and how are they in that case included.

### Finalizing the design

Show the final results of your project. Give your final thoughts on how you think the project went. What could have been done in an other way, or even better? Pictures are nice!

- [ ] Show final results of the project
- [ ] Pictures
- [ ] *Video presentation

---
