![Animated weather icons](https://github.com/user-attachments/assets/433a574c-948f-4211-8668-9500b47f6389)

# Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

## Problem definition

Cabbages are members of the Brassicaceae (Cruciferae) family which includes crops such as Kale, Cauliflower, Broccoli and Radish. One of the most widely grown, popular and nutritious vegetables in Japan mainly for the domestic market.The length of the total growing period varies between 90 (spring-sown) and 200 (autumn-sown) days, depending on climate, variety and planting date, but for good production the growing period is about 120 to 140 days. Most varieties can withstand a short period of frost of -6°C, some down to -l0°C. Long periods (30 to 60 days) of -5°C are harmful. The plants with leaves smaller than 3 cm will survive long periods of low temperature but when the leaves are 5 to 7 cm, the plant will initiate a seed stalk and this leads to a poor quality yield. Optimum growth occurs at a mean daily temperature of about 17°C with daily mean maximum of 24°C and minimum of 10°C. Mean relative humidity should be in the range of 60 to 90 percent.Our client owns the Cabbage field, which contains multiple greenhouses. Due to fluctuating temperature and humidity levels, the client struggles to maintain marvellous environmental conditions for their plants. These fluctuations, if not monitored, can lead to plant stress, producing smaller harvests and increasing the vulnerability to pests and diseases. Currently, the client lacks an efficient and working system where he can continuously monitor the changes in temperature and humidity. As a result of this issue, the cabbage field has been suffering massive losses on the harvests, causing stress and frustration among the local farmers. This situation has been noticed by the local businesses, who are extremely concerned and are considering changing their food suppliers as the quantity and quality of the products have decreased. The company's reputation in the local community was being ruined, so they approached us to create a solution. The owner, scared by this situation, requested our services to design a server to address the monitoring of environmental factors and ensure accurate data collection and real-time analysis, allowing fast and proactive actions to reduce risks and better manage the plant's development.

![cabbage1](https://github.com/user-attachments/assets/3bfcfbe5-cc7e-425b-b02d-4f99ceccfe10)


## Proposed Solution
Considering the client requirements an adequate solution includes a low cost sensing device for humidity and temperature and a custom data script that process and anaysis the samples acquired. For a low cost sensing device an adequate alternative is the DHT11 sensor[^1] which is offered online for less than 5 USD and provides adequare precision and range for the client requirements (Temperature Range: 0°C to 50°C, Humidity Range: 20% to 90%). Similar devices such as the DHT22, AHT20 or the AM2301B [^2] have higher specifications, however the DHT11 uses a simple serial communication (SPI) rather than more eleborated protocols such as the I2C used by the alternatives. For the range, precision and accuracy required in this applicaiton the DHT11 provides the best compromise. Connecting the DHT11 sensor to a computer requires a device that provides a Serial Port communication. A cheap and often used alternative for prototyping is the Arduino UNO microcontroller [^3]. "Arduino is an open-source electronics platform based on easy-to-use hardware and software"[^4]. In additon to the low cost of the Arduino (< 6USD), this devide is programable and expandable[^1]. I considered alternatives such diffeerent versions of the original Arduino but their size and price make them a less adequate solution.

Considering the budgetary constrains of the client and the hardware requirements, the software tool that I proposed for this solution is Python. Python's open-source nature and platform independence contribute to the long-term viability of the system. The use of Python simplifies potential future enhancements or modifications, allowing for seamless scalability without the need for extensive redevelopment [^5][^6]. In comparison to the alternative C or C++, which share similar features, Python is a High level programming language (HLL) with high abstraction [^7]. For example, memory management is automatic in Python whereas it is responsability of the C/C++ developer to allocate and free up memory [^7], this could result in faster applications but also memory problems. In addition a HLL language will allow me and future developers extend the solution or solve issues proptly.  

## Design Statement

Our team is developing a program using Arduino and DHT_11 sensors to monitor humidity and temperature required for the 
growing cabbage in greenhouses. The data will be uploaded to a real-time server within 48 hours and accessed via a secure login. This reliable, proven system will be ready within three weeks and will meet our client's needs (done using Pycharm)

## Success Criteria

[^1]: Industries, Adafruit. “DHT11 Basic Temperature-Humidity Sensor + Extras.” Adafruit Industries Blog RSS, https://www.adafruit.com/product/386. 
[^2]: Nelson, Carter. “Modern Replacements for DHT11 and dht22 Sensors.” Adafruit Learning System, https://learn.adafruit.com/modern-replacements-for-dht11-dht22-sensors/what-are-better-alternatives.   
[^3]:“How to Connect dht11 Sensor with Arduino Uno.” Arduino Project Hub, https://create.arduino.cc/projecthub/pibots555/how-to-connect-dht11-sensor-with-arduino-uno-f4d239.  
[^4]:Team, The Arduino. “What Is Arduino?: Arduino Documentation.” Arduino Documentation | Arduino Documentation, https://docs.arduino.cc/learn/starting-guide/whats-arduino.  
[^5]:Tino. “Tino/PyFirmata: Python Interface for the Firmata (Http://Firmata.org/) Protocol. It Is Compliant with Firmata 2.1. Any Help with Updating to 2.2 Is Welcome. the Capability Query Is Implemented, but the Pin State Query Feature Not Yet.” GitHub, https://github.com/tino/pyFirmata. 
[^6]:Python Geeks. “Advantages of Python: Disadvantages of Python.” Python Geeks, 26 June 2021, https://pythongeeks.org/advantages-disadvantages-of-python/. 
[^7]: Real Python. “Python vs C++: Selecting the Right Tool for the Job.” Real Python, Real Python, 19 June 2021, https://realpython.com/python-vs-cpp/#memory-management. 

1. The solution provides a visual representation of the Humidity and Temperature values outside the residences for a period of minimum 48 hours. The issue tackled here is the lack of a real-time monitoring system for tracking fluctuations in temperature and humidity in a cabbage field, which contains multiple greenhouses. This lack of monitoring has resulted in reduced harvest quality and quantity, pest and disease vulnerability, and multiple losses for the farm. By creating a system which can create a visual detailed representation of those fluctuations in the area over a 48-hour period, this will immediately allow our client to take action in order to control the temperature and humidity inside the greenhouses, reducing the losses, and protecting their reputation among the local community. This  monitoring and data analysis system is essential to ensuring the farm maintains ideal conditions for cabbage cultivation.
   
2. ```[HL]``` The local variables will be measured using a set of 2 sensors placed outside. One focused on collecting the temperature values and one focused on collecting the humidity data.
   
3. The solution provides a mathematical modelling for the Humidity and Temperature levels for each Local and Remote locations. ```(SL: linear model)```, ```(HL: non-lineal model)```
These models will allow our client to comprehend the fluctuations on the environmental conditions and take action in order to improve the quality and quantity of their products.

4. The solution provides a comparative analysis for the Humidity, Temperature (HL) levels for each Local and Remote locations including mean, standard deviation, minimum, maximum, and median.
   
5. ```(SL)```The Local samples are stored in a csv file and ```(HL)``` posted to the remote server as a backup.
   
6. The solution provides a prediction for the subsequent 12 hours for Humidity, and Temperature (HL). 
   
7. The solution includes a poster summarizing the visual representations, model and analysis created. The poster includes a recommendation about healthy levels for Humidity, and Temperature(HL). 

## TOK Connection
To what extent does ```the use of data science``` in climate research influence our understanding of environmental issues, and what knowledge questions arise regarding the ```reliability, interpretation, and ethical implications``` of data-driven approaches in addressing climate change

1. Impact on understanding of environmental issues

Modern use of data science can turn vast amounts of raw data into meaningful and understandable insights. For example, the temperature and humidity data collected through our project not only allows us to monitor the current state of the microclimate, but also to identify patterns such as seasonal fluctuations or critical periods for plants. This knowledge helps to develop strategies to prevent problems such as reduced yields due to unfavorable conditions. At the global level, analyzing climate data contributes to our understanding of phenomena such as global warming, changing precipitation or melting glaciers.

Knowledge questions arise regarding the: 

- Reliability
   1. Equipment accuracy: How reliable are sensors such as the DHT11 and what errors can occur during measurement?

   2. Human error: How can human errors, such as incorrect sensor settings or mistakes in data processing, impact the reliability and             accuracy of climate data analysis?

- Interpretation
   1. How does context affect interpretation? Different regions and cultures may have different understandings of what is considered              “ideal” growing conditions.

   2. Who interprets the data? Professionals with different experience and knowledge may come to different conclusions from the same data.

- Ethical implications
   1. How to ensure the confidentiality of the data collected?
  
   2. What measures should be taken to prevent misuse of environmental data, such as its use in competitive business practices or other           unethical activities?
   
2. What responsibilities do we have as technologists when it comes to handling personal data related to our living spaces?

   As technologists working with environmental data, we have a number of ethical, technical and social obligations. From an ethical 
   perspective, the understandability of data collection is essential. Customers must clearly understand what data is being collected, for 
   what purpose, and who will have access to it. In addition, we must ensure that this data is protected, using strong measures to guard 
   against leaks, breaches or unauthorized use. From a technical point of view, our obligations include collecting only the data needed for 
   a specific task, ensuring the reliability of the system to guarantee the accuracy and relevance of the data. From a social point of 
   view, it is important that the results of our analyses are not used for manipulative purposes, for example, to put undue pressure on the 
   customer. By respecting these responsibilities, we can create a system that is not only efficient, but also ethically sound and socially 
   responsible.
   
3. What cultural and contextual factors might impact our interpretation of the results, especially when comparing our local readings with those from the campus?

   Cultural and contextual factors play an important role in the interpretation of environmental data. Different regions have different 
   quality standards and traditional approaches to growing plants, which can influence the optimal conditions for crops such as cabbage. 
   For example, the ideal humidity for cabbage growth may differ depending on local traditions or cultural preferences. Conditions on the 
   farm and on campus can vary greatly, including factors such as the type of greenhouse, quality of equipment, and available resources. 
   Local climatic patterns, such as higher humidity in one area, may further affect data interpretation. In addition, the equipment used to 
   collect data on campus may be more advanced or accurate than on the farm, leading to differences in results. The microclimate on the 
   farm, which is influenced by factors such as shade, proximity to water sources, or wind exposure, may also differ significantly from the 
   microclimate on the campus, further complicating the comparison of data at these locations.


# Criteria B: Design

## System Diagram **HL**
![2 min](https://github.com/user-attachments/assets/17e07aee-1474-40d4-bcb2-bc59d136aa8b)

**Fig.1** shows the system diagram for the proposed solution (HL). Outdoor humidity and temperature data will be measured using an Arduino and a DHT11 sensor that is positioned so that it records data from the outside. The variables will be queried on the remote server using a GET request to the server API at 192.168.4.137. The local values are stored in a CSV database locally and a backup copy will be store in the remote server using the Weather API.

![image](https://github.com/user-attachments/assets/01c6219e-5bdd-4bb0-ac22-b202cb1446b4)
**Fig.2** shows the hardware architecture of the Arduino. The Arduino is connected to the computer using a USB cable. The DHT11 sensors are connected to the Arduino pins as shown in the figure. The Arduino is powered from the computer using a USB cable.

![image](https://github.com/user-attachments/assets/f15d3bf7-9944-4364-842d-1b58a42941b9)
**Fig.3** shows the location of the setup in the room. The laptop and Arduino are placed on the windowsill so that the DHT 11 sensor faces the outside and measures the temperature and humidity data from outside. 

## Flow Diagrams

![1flowdiagram drawio (1)](https://github.com/user-attachments/assets/c6796788-5b1b-4519-afcb-40194442d65c)
**Fig.4** this flow diagram represents a program that connects to an Arduino, continuously reads sensor data for 48 hours, extracts humidity and temperature values, and saves them in a timestamped CSV file for later analysis.

![2flowdiagram drawio](https://github.com/user-attachments/assets/5d8ee792-5459-46fd-a87e-f7112ba1107a)
**Fig.5** this flow diagram represents the sequence of operations in an Arduino program that records temperature and humidity data from a DHT11 sensor for 48 hours.

## Record of Tasks
| Task No | Planned Action                                           | Planned outcome                                        | Time estimate | Date of reaching the target | Criterion |
|---------|----------------------------------------------------------|--------------------------------------------------------|---------------|-----------------------------|-----------|
| 1       | Formulate the problem definition and upload it on GitHub | Clear understanding of the problem                     | 20 min        | Nov 26                      | A         |
| 2       | Make a list of required materials                        | The finished list of materials                         | 5 min         | Nov 27                      | B         |
| 3       | Formulate design statement                               | Completed statement which addresses client need        | 15 min        | Nov 27                      | A         |
| 4       | Code and upload program for Arduino on Arduino IDE       | Arduino programmed to collect data                     | 45 min        | Nov 29                      | C         |
| 5       | Construct Arduino Circuit for data collection            | Sensors connected and ready for data collection        | 30 min        | Nov 29                      | C         |
| 6       | Form Test Plan                                           | Test plans outlined for solution development           | 1 hr          | Nov 29                      | B         |
| 7       | Test serial connection between Arduino and computer      | Confirm serial connection is functional                | 30 min        | Nov 29                      | C         |
| 8       | Test DHT11 Sensor and its connection to Arduino          | Verify sensor returns valid readings                   | 15 min        | Nov 29                      | C         |
| 9       | Code data collection method on PyCharm                   | Program retrieves data every 2 seconds                 | 30 min        | Nov 30                      | C         |
| 10      | Test if readings can be saved to a CSV file              | Confirm successful saving of readings                  | 15 min        | Nov 30                      | C         |
| 11      | Test if readings can be sent to a remote server          | Confirm data can be posted to remote server            | 20 min        | Nov 30                      | C         |
| 12      | Code data storage method on PyCharm                      | Store data locally (CSV) and remotely                  | 1 hr          | Dec 2                       | C         |
| 13      | Test and finalize hardware and software                  | Resolve bugs and finalize for final data collection    | 1 hr          | Dec 2                       | C         |
| 14      | Collect temperature and humidity data for 48 hours       | Gather 48 hours of data from sensors                   | 48 hr         | Dec 2 - Dec 4               | C         |
| 15      | Create flow diagrams and reference figures               | Visual diagrams for process and analysis               | 2 hr          | Dec 5                       | B         |
| 16      | Construct graphs using Pyplot                            | Generate raw data and averaged graphs using Matplotlib | 3 hr          | Dec 5                       | C/D       |
| 17      | Conduct usability testing for graphs                     | Finalize graphs for readability and usability          | 30 min        | Dec 6                       | D         |
| 18      | Design a poster                                          | Create poster summarizing findings and investigation   | 3 hr          | Dec 7                       | D         |
| 19      | Film video introducing product                           | Film a presentation showcasing the final solution      | 1 hr          | Dec 8                       | D         |
| 20      | Finish the github repository and the details             | Get a completed and successful repository on Github    | 30 min        | Dec 8                       | C         |
## Test Plan (check the drive of the video for the arduino tutorial video)
| Test type                                  | Objective                                                                                                                                                                   | Procedure                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Expected Output                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Technical:   Arduino Set Up          | Verify if the arduino is properly arranged and connected to the computer.                                                                                                   | 1. Check if all the components are present, you're supposed to have:   -One Arduino UNO R3 Board (**Fig.4**)  -One DHT11 sensor (**Fig.5**)  -One HDMI cable (**Fig.6**)  -Three wires with different colours(**Fig.7**)  2. If you have all the objects, then check if one side of the wires are connected to the three pins of the sensor. The other side of the first wire must be connected to the 3.3V pin, the middle wire must be connected to the pin 2 of the board, the last wire must be connected to the GND pin. Finally, connect the arduino board to the computer using the HDMI cable. If everything is correct, continue to the next step, if not, watch the video on the end of this table teaching how to set up the arduino board.  3.Place the computer in a safe space where it can collect the data non-stop, the computer can be inside a building, however make sure the sensor is outside. In our project we placed the computer on a window, as you can see in **Fig.8**. Just remember your computer must be  connected to the internet and charging as the data collecting will take a long time. | The arduino must be properly arranged and placed in a safe space in order to start the  collection of data.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|      Functionality:  Arduino Code          | Verify if the arduino code is working and collecting real-time data.                                                                                                        | 1. Open the Arduino IDE, which is the open-source Arduino Software (IDE), making it easy to write code and upload it to the board. This  software can be used with any Arduino and if your computer doesn't have it, you can download on the following link: https://www.arduino.cc/en/software  2. After opening the Arduino IDE, you must check if the correct board and port are selected as shown in **Fig.9**  3. Check if the code you have is the same as in **Fig.10**  4. Verify and upload the code, the button to verify looks like a V and the button to upload is an arrow. Wait until the messages "verification complete" and "upload complete" show in your screen.                                                                                                                                                                                                                                                                                                                                                                                                                                            | The program should run and starts collecting the data. You must make sure that all sensors are working, and that your screen is the same as in Fig.11                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|      Functionality:  Pycharm Code - CSV    | Verify if the pycharm code is working, and the data collected is being transformed in a csv file and sending this data to the server.                                       | 1. Open the Pycharm Program, and check if the interpreter is the Python 3.13. You're able to download Pycharm here: https://www.jetbrains.com/ja-jp/pycharm/ and Python 3.13 here:  https://www.python.org/downloads/  2. The code you're seeing must be the same as in Fig.12, if it is, then proceed to step 3. If the code is different, then please correct.  3. Click to run the code, wait a couple seconds, and the data being collected should appear on your screen.  4. Now, open the library of the computer, click on Acer C:, then users, then Lais, then Pycharmprojects, and finally Pycharmproject2. You should be able to  see a csv file named Data with the date and time you started recording. Open this file and check if the data collected is there. Check if data is being  collected and uploaded to the server by looking at the adequate sensor id and see if it matches the id of sensors used for the data collecting.                                                                                                                                                                           | The program must run and transform the data  collected in a csv file stored in your computer. Make sure that all sensors are collecting data,  and uploading it onto both a .csv file and the  remote server.The program contains a return that is visible and which is stored in a csv file in  order to prove that the program ran successfully. The program must be able to run if the computer  goes into rest mode. The program should continue  to run without stopping until the final time of  48 hours, and the data should continue to be  collected.                                                                                      |
|      Functionality:  Pycharm Code - Graphs | Verify if the code to formulate the non-lineal model graphs is working, in order to be able to have a full comprehension of the current problem and take action towards it. | 1. Move to the Pycharm tab called "graphsproject2". Please make sure the package matplotlib is installed.  2. Check if the code you're seeing is the same as showed in Fig.13. If it is, then proceed to the next step, if it's not, please correct the code based on the image.  3. Run the code, type which data you want to analyze: Temperature, Humidity, Temperature X Humidity, Average Temperature, Average Humidity. You should see  the plot of the data showed as a non-lineal model with the proper features like labels as Time and Temperature, Grid, and colour.The model you should see  must look something like in Fig.14, however keep in mind that it will not look exactly the same as the data we used and the data you're using right now  are different sets of data.                                                                                                                                                                                                                                                                                                                                  | Each program must run and print the appropriate non lineal model based on the code being ran. The user  should see a model, containig correct features like  x-axis and y-axis labels, colors, grid, and title. Make sure your graph is done according to the data collected. They must be able to answer what kind of  data each graph is expressing (example: when looking at  the average of temperature, they should be able to say  that they see the average of the 2 temperature values being  plotted). If this test fails for any of the graphs, there is  a need to make adjustments, such as adding labels, using  different colors, etc. |
|   Errors Test:  Pycharm Code               | Test if the program has any errors or glitches due to the amount of time the program is ran for (48 hours) and for the amount of data being  collected.                     | 1. Go back to the Pycharm program and run continuously.  2. Check every 3 hours if the program is running non-stop without any problems.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | All the data was collected in real-time and the program ran for the required time without any glitches.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

# Criteria C: Development

## List of techniques used
01. For Loop 
02. While Loop  
03. If/Else Statements  
04. Functions 
05. Lists and Dictionaries 
06. Libraries:
    * Comma Separated Values (CSV) Files 
    * Serial Communication
    * Application Programming Interface (API)
    * Pandas
    * Matplotlib
    * Time
    * Requests
    * Numpy
    * DHT Sensor Library (Library used in Arduino) 
07.Try and Accept Commands 
08.Registering and Login into API 

## List of Libraries Used

PyCharm: csv, time, datetime, requests, matplotlib, numpy, pandas, serial, api

Arduino IDE: DHT Sensor Library

## Development

## Code from Arduino IDE

**Success Criteria: As seen in the success criteria, the criteria 2 states that the local variables will be measured using a set of 2 sensors placed outside. One focused on collecting the temperature values and one focused on collecting the humidity data. On code, we demonstrate the sensors being used, connecting them to the arduino, collecting the data and meeting the criteria 2.**

With a view to collect and read the data from the DHT sensors, it is a must to create, verify, and upload a program to the Arduino controller. This process is realized using the Arduino Integrated Development Environment(IDE), which is a platform that connects to the Arduino boards to upload programs and communicate with them. Programs written using Arduino Software (IDE) are called sketches. These sketches are written in the text editor and are saved with the file extension .ino. Uploading the compiled code allows the sensors to collect the data needed and process properly. Below is the code we developed for this task, split by parts so we can explain its functionality:


```.C++
#include "DHT.h"

#define DHTPIN 2     // what pin we're connected to
#define DHTTYPE DHT11   // DHT 11

// Create the dht object
DHT dht(DHTPIN, DHTTYPE);
static unsigned long startTime;
```
**Code Partial Overview: In the first line of the code, we must include the DHT.h library, in this case we will be using the Adafruit DHT Sensor Library. This library is essential for the program as it makes the arduino to identify the and send the commands to the DHT sensors connected to it. In the lines 3 and 4, we defined the pin the sensor is connected to and the type of sensor it is being used in this case scenario. The sensors being used for our project are the DHT11 type, and they are connected to pin 2. The pin and sensor can be seen in the fig.2 located in the Criteria B. On the line 7, the sensor's identity is created so later on the sensor can be called on other programs. Finally, on the line 8, the variable "startTime" is declared and assigned to the type Unsigned long, which permits the variable to store a large amount of non-negative integer values. The word static ensures that the variable retainsits value between function calls. This last line is used to store the timestamp of the data collect, to be exact the start of the collection.**

```.C++
void setup() {
  Serial.begin(9600);
  while (!Serial) delay(10); // Wait for Serial monitor to be ready
  // Serial.println("DHTxx start!");

  dht.begin();
  startTime = millis();
}
```

**Code Partial Overview: Next, in this section, we define the setup of the arduino, which is executed once the arduino code is uploaded and ran. On the second line of this code, we start the serial communication between the arduino and the computer, using Serial.begin(9600). This command makes the baud rate, which is the data rate in bits per second, be 9600 enabling the arduino to send and receive data. On the line 3, we used a while loop to make sure the serial is ready before starting the process. The loop checks the serial interface using !Serial and pauses for 10 milliseconds using delay(10) until the serial is working. This helps to ensure the process will flow without any errors, as some serial interfaces require time to initialize. Next, we start the DHT sensor by typing the command dht.begin(), this prepares the sensor to take readings. Finally, we record the time in milliseconds using millis() and store in the startTime variable.**

```.C++
void loop() {
  // Record for 48 hours (48 * 60 * 60 * 1000 milliseconds)
  //static unsigned long startTime = millis();
  if (millis() - startTime > 48 * 60 * 60 * 1000UL) {
  //if (millis() - startTime > 10 * 1000UL) {  // Short test
    Serial.println("48-hour recording complete.");
    while (1); // Stop the program after 48 hours
  }

  // Wait 2 second between measurements
  delay(2000);

  // Reading temperature or humidity takes about 250 milliseconds!
  float h = dht.readHumidity();
  float t = dht.readTemperature();
```

**Code Partial Overview: In this part, a loop is intiated to collect and record the data from the sensors and monitor the time. As shown in line 4, first the program checks whether the total time has exceeded 48 hours(the comment demonstrates the calculation as 48 x 60 x 60 x 1000(milliseconds)). It does rgar by comparing the difference between the current time and the stored in the variable startTime. If the time of 48 hours has passes, the program prints a message "48-hour recording complete", and it stops the program by entering an infinite loop (while(1)). Next, the program requests the arduino to wair for 2000 milliseconds, or 2 seconds, between each collection using delay(2000). This delay helps the data collection to be more effective, excluding unnecessary readings and avoiding glitches. Finally, the program reads the humidity and temperature data from the dht sensor, storing the values in the real number variables h(for humidity) and t (temperature), respectively.**

```.C++
  if (isnan(h) || isnan(t)) {
    Serial.println("Failed to read from DHT sensor!");
  }else 
```
**Code Partial Overview: Within the loop, the program will verify if the DHT sensor readings are valid. In the If statement, the program uses the isnan() function to check if the humidity or the temperature value is not a number. If the value is considered invalid, the program will print "Failed to read from DHT sensor!" to the serial monitor. This step makes sure we won't have any mistakes on the data collection.**

```.C++
 {
 // Print readings to Serial Monitor
 Serial.print("Humidity: ");
 Serial.print(h);
 Serial.print(" %\t");
 Serial.print("Temperature: ");
 Serial.print(t);
 Serial.println(" *C ");
  }
  }
```
**Code Partial Overview: After ensuring there are no errors in the sensor readings, the program will print the collected humidity and temperature values to the serial monitor. This step will help us to transfer the data to Pycharm, where we will process further and analyze it. In our project, the data will be sent in a structured format. For each reading, the program uses Serial.print() to print the label(example, "Humidity:"), the corresponding value, and the unit. To print formatted, the Serial.print() function is repeated multiple times, we chose to do this as is considered the best in arduino programming when printing multiple variables on the same line, also because it was the way we learned in class. We chose to separate the values for humidity and temperature in two split variables so later on will be easier to analyze in Pycharm, this format also makes it easier to read and understand. Finally, the Serial.print() function is used to display the humidity percentage and temperature in degrees Celsius.**

## Code from Pycharm

**Success Criteria: As seen in the success criteria, the criteria 2 states that the local variables will be measured using a set of 2 sensors placed outside. One focused on collecting the temperature values and one focused on collecting the humidity data. On code, we demonstrate the sensors being used, connecting them to the arduino, collecting the data and meeting the criteria 2.**

 **```(SL)```The Local samples are stored in a csv file and ```(HL)``` posted to the remote server as a backup.**

### Code 1: Registering the sensors
**When using the Pycharm, we identified the need to be able to connect with our remote server in order to back up our data. As you can see in the following code, the register of the sensors is made:**


```.py
from datetime import datetime
import time
import serial
import requests

# Arduino serial setup (update 'COM3' to your port)
arduino = serial.Serial(port='COM3', baudrate=9600, timeout=1)

# Server details
server_ip = "192.168.4.137"  # Replace with your server IP
user = {"username": "cabbage_field", "password": "laisalena"}
```
**To enable the communication between the computer and the arduino and a server, it is necessary to import the libraries. The datetime and time libraries are imported in order to manage the 48 hours of data which we will be collecting. The serial library is imported, this library is the one which will make the connection between the arduino and the computer. The request library is imported to facilitate the HTTP requests, this will allow us to send and get data from the server.**
**The Arduino's connection with serial is setup by creating the serial object using serial.Serial. This object will be assigned to the new variable "arduino", using the serial.Serial we must add the port based on the arduino's port, the baud rate (which we set to 9600, determining the speed), and timeout of 1 second, which will define how long the program should wait.**
**In order to interact with the server's, the IP address(192.268.4.137) is stored in the variable server_ip. The user information required for the authentication are store in the server in the user dictionary. The dictionary contain username and password for each user. In our project, we defined our username as cabbage_field and password as laisalena.**

```.py
# Register and login
print("Registering user...")
requests.post(f"http://{server_ip}/register", json=user)
```
**Next, to register the server, the program will print "Registering user...", so the user can identify what action is being done. As it follows, the program sends a POST request to the server, this request uses /register endpoint and includes the user data in JSON format. This is only necessary one time, because we don't need to register ourselves more than once. Once the request is sent, we can proceed to the next step. **

```.py
print("Logging in...")
req = requests.post(f"http://{server_ip}/login", json=user)
access_token = req.json()["access_token"]
auth = {"Authorization": f"Bearer {access_token}"}
```
**After registering a user, we have to log in so we can access all the features of the server. The first line prints ("Logging in...") indicating to the user that the program is running. The access token, which will be provided by the server, is extracted from the JSOn response and stored in the new variable access_token, as shown in access_token = req.json()["access_token"]. In the line 4, the access token is included in the authorization header, being saved in a dictionary called auth. The dictionary assign the token to "Authorization", as shown in {"Authorization": f"Bearer {access_token}"}. All of this saved in the dictionary auth, this simplifies the process of including the authorization header in next requests**

```.py
# Create temperature and humidity sensors
print("Creating sensors...")
sensor_temp = {
    "type": "Temperature",
    "location": "hondafield",
    "name": "sensor_cftemp",
    "unit": "C"
}
sensor_hum = {
    "type": "Humidity",
    "location": "hondafield",
    "name": "sensor_cfhum",
    "unit": "%"
}
# Post sensors to the server
req_temp = requests.post(f"http://{server_ip}/sensor/new", json=sensor_temp, headers=auth)
sensor_temp_id = req_temp.json()["id"]
print(f"Temperature sensor created: ID {sensor_temp_id}")

req_hum = requests.post(f"http://{server_ip}/sensor/new", json=sensor_hum, headers=auth)
sensor_hum_id = req_hum.json()["id"]
print(f"Humidity sensor created: ID {sensor_hum_id}")
```
**Then, we must create the sensors that will represent the device collecting the temperature and humidity data, we did this by creating dictionaries in python, each representing an aspect of the sensor. In the first line of the code, we print "Creating sensors...", again as a way to inform the user of the action being processed. As we follow up, we create a dictionary called sensor_temp to represent the temperature sensor, this dictionary includes the following information:**
**-Type: Temperature**
**-Location: hondafield**
**-Name: sensor_cftemp**
**-Unit: C**
**Similarly, we create a second dictionary called sensor_hum to represent the humidity sensor, the structure is the same for both sensors, just different values are assigned. As you can see below:**
**-Type: Humidity**
**-Location: hondafield**
**-Name: sensor_cfhum**
**-Unit: %**
**These dictionaries are the base for managing our sensor, making sure the data collected will be processed and stored. Each dictionary can be used later on to interact with the server.**

### Code 2: Solution X CSV file

```.py
import serial
import csv
from datetime import datetime

now = datetime.now()
data_file_name = 'Data_'+now.strftime("%Y%m%d%H%M%S")+'.csv'
with open(data_file_name, mode='w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(["Time (s)", "Humidity (%)", "Temperature (C)" ])  # Write header
```
**In order to save all the data we have been collecting during the experiment, we have to create a CSV file to store the measurements in an organized way. We did by importint the csv library for writing the csv file and the datetime library to create and manage the time. We also imported the pyserial library in order to connect with the arduino and collect the data. In the line 5, we assigned the variable now to the datetime.now() function, which is used to get the current date and time. Following up, the strftime() method was used to format the current time and date throughout the experiment in the format of YYYYMMDDHHMMSS(year, month, day, hour, minute, seconds). The string is connected to Data_ and the file extension .csv, as you can see in data_file_name = 'Data_'+now.strftime("%Y%m%d%H%M%S")+'.csv'. This is a step that helps to identify the data files being created.**
**Then, we open a new file with this name in write mode(thats why is 'w') using the function open(), also adding newline='' by then end to make sure the file will print one set of data per line. Inside the with open, we use the function csv.writer(), this is stored in a variable and will be used to write data to the file. Finally, we use the write.writerow() function to write the header of the csv file as "Time (s)", "Humidity (%)", "Temperature (C)", this will help organize the data collected.**

```.py
print("Time (s)", "Humidity (%)", "Temperature (C)")
# Replace 'COM5' with the actual port your Arduino is connected to
# Also, update the baud rate if necessary (default is 9600)
arduino = serial.Serial(port='COM5', baudrate=9600, timeout=5)
time = 0
##for i in range(5):
line = arduino.readline().decode('utf-8')
```
**In this part of the code, we start by using the print() command, again to create a header for the data being read. The header must show "Time (s)," "Humidity (%)," and "Temperature (C)" to indicate each type of data being collected. This makes the data more organized and easier to analyze. Next, we must start a connection with the arduino, so we use the serial.Serial() function, again we have to specify the port which the arduino is connected to the arduino, in this case was the COM5. Again, we sete the baud rate to 9600 which will match the data transmitted between the arduino and the computer. And a timeout of 5 seconds before moving on. After finalizing this step, we have the variable named time, which we will set its value to 0, this variable is the one that will monitor the real time values. Finally, we end this step using the function readline() to read the data collected by the arduino, and as the data is in bytes we use the function .decode('utf-8') to make the data humanly understandable. This whole process will ensure we have the data for time, humidity, and temperature without any mistakes.**

```.py
while not line.startswith('48-hour'):
    line = arduino.readline().decode('utf-8')
    print(time, line, end="")
    if line.startswith('Humidity: '):
        #print(line[10:15], line[31:36])
        with open(data_file_name, mode='a', newline='') as file:
            writer = csv.writer(file)
            writer.writerow([time ,line[10:15], line[31:36]])

    time += 2

print("finish")
arduino.close()
```
**As require by the success criteria, we must collect data for 48-hours so we start this part of the code with a loop which will check if the current line of data doesn't start with the string '48-hour'. This will make sure the program will read for all the required time and process until the 48 hours collection is finished. Then inside the loop, our program reads the line of data using the function read.line(), which retrieves the next avaiable line. The line then is decoded from bytes into a UTF-8 string as you can see in the code before. The program will print the current time in seconds along with the data collected. If the line starts with 'Humidity: ', for example, the program will get specific parts of the line of collected data, so the humidity value. These values are then written into the csv file, using the csv.writer function, this will make sure we won't miss anything and all data will be recorded. The time vvariable is only to give some time between each reading, in this case 2 seconds. Finally, when the loop of 48 hours exit, the program will print "finish".**

![Captura de tela 2024-12-09 012339](https://github.com/user-attachments/assets/a49d9339-78e7-4846-aba5-86ec64727657)


### Code 3: Graphs and Visual Representation

**Success Criteria:

The solution provides a mathematical modelling for the Humidity and Temperature levels for each Local and Remote locations. ```(SL: linear model)```, ```(HL: non-lineal model)```**

**The solution provides a comparative analysis for the Humidity, Temperature (HL) levels for each Local and Remote locations including mean, standard deviation, minimum, maximum, and median.**
   
**The solution provides a prediction for the subsequent 12 hours for Humidity, and Temperature (HL).**
   

```.py
from matplotlib import pyplot as plt
import pandas as pd
from datetime import datetime
import numpy as np
import requests

start_datetime = datetime(2024, 12, 6, 21, 56)
window_size = 1000
```
**The code above aims to set up the necessary tools to process and analyze data. First, it imports the libraries we need to handle data, time, and plotting. The matplotlib.pyplot library is used for creating graphs, pandas is used for managing and analyzing data, and datetime helps work with specific dates and times. Additionally, numpy is imported for numerical operations, and requests is for getting the data from the server.Then we define the variable start_datetime to december 6, 2024 at 21:56. Finally, window_size is set to 1000, which could indicate a chunk of data or a range for analysis. This setup will be used to analyze the temperature or humidity. However, in the case of the Karuizawa weather data, the server data wasn't available when local measurements were taken.**

```.py
choose_data = input("Select a (L)ocal (default) or (R)emote: \n")

if choose_data.lower().startswith('r') :
    print('Remote data')
    server_ip = '192.168.4.137'

    temperature_id = 409
    humidity_id = 410
    data_label = 'Remote Data'

    request = requests.get(f"http://{server_ip}/readings")
    data = request.json()
    #
    # data = data1
    #
    sensors = data['readings'][0]
```
**In order to collect the temperature and humidity values from the remote server, which in our case wasn't avaiable, along with the local measurements, we added the function to get the data from the specific server. However the code depends on the servers avaiability, and during the time we collected, it wasn't avaiable. Next, the user is requested to select between a local and remote data with choose_data = input("Select a (L)ocal (default) or (R)emote: \n"), if the user press r then the computer identifies the remote option. For the remote data, the server previously mentioned is required (192.168.4.137) is used to request data, the requests.get function gets the readings from the server and the server response is expected to be JSON format, and the json() method extracts the data for processing later. The variable sensors is assigned to the first element on the list.**

```.py
temperature_values = [s['value'] for s in sensors if s['sensor_id'] == temperature_id]
    index_data = [datetime.strptime(s['datetime'][:16], "%Y-%m-%dT%H:%M") for s in sensors if s['sensor_id'] == temperature_id]

    humidity_list = [s['value'] for s in sensors if s['sensor_id'] == humidity_id]
    # humidity_index = [datetime.strptime(s['datetime'][:16], "%Y-%m-%dT%H:%M") for s in sensors if s['sensor_id'] == humidity_id]
    # time = [datetime.strftime(s['datetime'][:16], "%Y-%m-%dT%H:%M") for s in sensors if s['sensor_id'] == temperature_id]
    # time =
    time = [0] + [(index_data[i] - index_data[0]).seconds for i in range(1, len(index_data))]

    df = pd.DataFrame({'Time (s)':time,'Humidity (%)':humidity_list,'Temperature (ºC)':temperature_values},
                      index=index_data)
```

**The code above processes the data in order to organize the temperature and humidity readings with the time they were collected. This part of the code is a bit more complicated so we will split in parts in order to explain better:**

```.py
temperature_values = [s['value'] for s in sensors if s['sensor_id'] == temperature_id]
```
**This first line "filters" the data collected and collects the value of each entry where the id matches the temperature id, creating a list of temperature readings from the dataset.**

```.py
index_data = [datetime.strptime(s['datetime'][:16], "%Y-%m-%dT%H:%M") for s in sensors if s['sensor_id'] == temperature_id]
```
**This line gets the time and converts with the temperature readings. It makes sure the datetime format is the same, matching the first 16 characters pf the datetime string.**

```.py
humidity_list = [s['value'] for s in sensors if s['sensor_id'] == humidity_id]
    # humidity_index = [datetime.strptime(s['datetime'][:16], "%Y-%m-%dT%H:%M") 
```
**Similar to the temperature data, this line filters for humidity data based on the humidity_id and creates a list of humidity readings.**

```.py
time = [0] + [(index_data[i] - index_data[0]).seconds for i in range(1, len(index_data))]
```
**Here, the list of the time values in seconds is created. The first time value is defined as 0 to represent the start time. For each timestamp, the difference from the first one is calculated.**
```.py
df = pd.DataFrame({'Time (s)':time,'Humidity (%)':humidity_list,'Temperature (ºC)':temperature_values}, index=index_data)
```
**Here, a pandas dataframe is creayed to oragnize the data.**
```.py
else:
    print('Local data')
    df = pd.read_csv('Data_20241206100513.csv')
    time_local = pd.date_range(start=start_datetime, periods=df.shape[0], freq='2s')
    df.index = time_local
    data_label = 'Local Data'
```
**The part of the code above checks the condition, and execute the else if the condition is false. It prints "Local data" and then reads the CSV file named Data_20241206100513.csv into a Pandas DataFrame. A datetime index is created using pd.date_range, starting from a specified start_datetime, spanning the number of rows in the DataFrame, and incrasing by 2 seconds (freq='2s'). Finally, the variable data_label is set to "Local Data" to label the data source.**

```.py
choose_measure = input("Select measure (T)emperature (default) or (H)umidity: \n")

if choose_measure.lower().startswith('h'):
    col = 1
else:
    col = 2


choose = input("Select a graph: \n"
               "\tA-Original\n"
               "\tB-Averaged\n"
               "\tC-Standard Deviation\n"
               "\tD-Quadratic Model\n"
               "\tE-Quatric Model\n"
               "\tF-Quadratic Model for next 12 hours\n"
               "\tG-Quatric Model for next 12 hours\n"
               )
```
**This part of the code requires the user to select the measurement they want and assign to the corresponding column, then asks the person to choose one of all the graphing options by entering the proper letter for the option.**

```.py
subsequent_time = pd.date_range(start= df.index[-1], periods = 12*60*30, freq='2s')
```
**The code creates a DatetimeIndex called subsequent_time using the pd.date_range function from pandas. It starts from the last timestamp in the DataFrame df(df.index[-1]), generating a total of 12 * 60 * 30 time (corresponding to 30 hours at 2-second intervals). This results in a time series that continues from the end of the DataFrame's index, with a total duration of 30 hours.**

```.py
if choose.upper() == 'A':
    # Original
    plt.plot(df.iloc[:, col],'r')
    plt.legend(['Original'])
```
![Local_Temperature_Original](https://github.com/user-attachments/assets/9935ce65-41b8-4783-9272-0ff723f3b32c)

![Local_Humidity_Original](https://github.com/user-attachments/assets/fe927ed4-fb8b-47ba-9fbc-03d0513e15dd)

**The code checks if the variable choose, converted to uppercase, is equal to 'A'. If its true, it uses Matplotlib to plot the data from a specific column of a DataFrame in red. It also adds a legend to the plot with the label 'Original'.**

```.py
elif choose.upper() == 'B':
    # Averaged
    plt.plot(df.rolling(window=window_size).mean().iloc[:, col], 'k')
    plt.legend(['Averaged'])
```
![Local_Temperature_Averaged](https://github.com/user-attachments/assets/0b165ce4-4175-4449-a0da-321584ffea2d)

![Local_Humidity_Averaged](https://github.com/user-attachments/assets/fdaaef7a-3130-4161-bf40-c84bc11f5a5f)

**The code checks if the variable choose, converted to uppercase, is equal to 'B'. If its true, it calculates the moving average of the specific column in the dataframe using the defined window_size. The moving average smooths the data by averaging values within the window. The resulting averaged data is then plotted as a black line using Matplotlib, and a legend labeled 'Averaged' is added to the plot.**

```.py
elif choose.upper() == 'C':
    # Standard Deviation Temperature
    plt.plot(df.rolling(window=window_size).std().iloc[:, col], 'b')
    plt.legend(['Standard Deviation'])
```
![Local_Temperature_Std](https://github.com/user-attachments/assets/efabfd1a-f5ad-48ba-8592-8160ae1d76c5)

![Local_Humidity_Std](https://github.com/user-attachments/assets/5f91c7da-2191-4c24-a498-5b9497915688)

**The code checks if the user's input, variable choose is "C". If its true, it calculates the moving standard deviation of a specific column in the DataFrame using the window_size. Then, it plots the moving standard deviation values in blue 'b' and shows a legend labeled "Standard Deviation" on the plot.**

```.py
elif choose.upper() == 'D' or choose.upper() == 'E' or choose.upper() == 'F' or choose.upper() == 'G':
    if choose.upper() == 'D' or choose.upper() == 'F':
        # Quadratic Model
        coeff = np.polyfit(df.iloc[:, 0], df.iloc[:, col], 2)
    else:
        # Quatric Model
        coeff = np.polyfit(df.iloc[:, 0], df.iloc[:, col], 4)

    model = np.poly1d(coeff)

    subsequent_time = pd.date_range(start=time_local[-1], periods=12 * 60 * 30, freq='2s')
    t = [2 * i for i in range(12 * 60 * 30)]
```
**The code checks if the variable choose shows to letters ('D', 'E', 'F', or 'G'), and based on further conditions, it proceeds either a quadratic or quatric polynomial model to the data in a specified column using np.polyfit. A quadratic model is selected if choose is 'D' or 'F', while a quatric model is used for 'E' or 'G'. The resulting polynomial model is then used to predict values over the time of data collected, 12 hours at 2-second intervals, with time represented in seconds.**

```.py
 if choose.upper() == 'D':
        # Quadratic Model
        plt.plot(df.iloc[:, col], 'r')
        plt.plot(df.index, model(df.iloc[:, 0]), 'g')
        plt.legend(['Original', f'Quadratic: {coeff[0]}t²+{coeff[1]}t+{coeff[2]}'])
```
![Local_Temperature_Quadratic](https://github.com/user-attachments/assets/1f893fda-4f1f-4812-9122-e8b8c1357f3f)

![Local_Humidity_Quadratic](https://github.com/user-attachments/assets/d4c42e8d-530a-4fc4-b45a-bedd7e1a6247)

**The code checks if the user input is 'D', selecting the quadratic model. If its true, it plots two lines on a graph using matplotlib: the original data from the specified column in red and the quadratic model in green. It then adds a legend showing the labels for both the original data and the quadratic model equation.**

```.py
    elif choose.upper() == 'E':
        # Quatric Model
        plt.plot(df.iloc[:, col], 'r')
        plt.plot(df.index, model(df.iloc[:, 0]), 'g')
        plt.legend(['Original', f'Quatric: {coeff[0]}$t^4$+{coeff[1]}t³+{coeff[2]}t²+{coeff[3]}t+{coeff[4]}'])
```
![Local_Temperature_Quatric](https://github.com/user-attachments/assets/eb0ac129-b76a-42fd-a7c3-c8f52e53f721)

![Local_Humidity_Quatric](https://github.com/user-attachments/assets/19e0ea57-7783-440e-a45b-20ff94481c27)

**The code checks if the user input is 'E', selecting the quatric model. If its true, it plots two lines on a graph using matplotlib: the original data from the specified column in red and the quadtric model in green. It then adds a legend showing the labels for both the original data and the quatric model equation.**

```.py
 elif choose.upper() == 'F':
        # Quadratic Model for next 12 hours
        plt.plot(subsequent_time, model(t), 'g')
        plt.legend([f'Quadratic: {coeff[0]}t²+{coeff[1]}t+{coeff[2]}'])
```
![Local_Temperature_Quadratic_Next12h](https://github.com/user-attachments/assets/313199aa-f17c-4947-9e9a-0787814e2c1b)

![Local_Humidity_Quadratic_Next12h](https://github.com/user-attachments/assets/8d91fe85-43a0-47df-b1af-d3197a596833)

**The code checks if the user input is 'F', selecting the quadratic model prediction for the next 12 hours. If its true, it plots the quadratic model line predicting the next 12 hours of data.**

```.py
    elif choose.upper() == 'G':
        # Quatric Model for next 12 hours
        plt.plot(subsequent_time, model(t), 'g')
        plt.legend([f'Quatric: {coeff[0]}$t^4$+{coeff[1]}t³+{coeff[2]}t²+{coeff[3]}t+{coeff[4]}'])
```
![Local_Temperature_Quatric_Next12h](https://github.com/user-attachments/assets/ff778839-3aa0-4717-82b6-804ad7cef433)

![Local_Humidity_Quatric_Next12h](https://github.com/user-attachments/assets/a5bd62cd-c179-45a3-a2b2-4e71243d1dae)

**The code checks if the user input is 'G', selecting the quatric model prediction for the next 12 hours. If its true, it plots the quatric model line predicting the next 12 hours of data.**

```.py
else:
    print('No available option was chose. Ending!')
```
**This code checks if the previous condition is true, if not, then the command else is executed and it prints "No available option was chose. Ending!"**

```.py
plt.grid()
plt.xticks(rotation=45)
plt.xlabel('Date time (day-hours)')
plt.ylabel(df.columns[col])
plt.title(data_label)
plt.show()
```

**The code above is used to customize and show the plots using Matplotlib. It enables the grid, rotates the x-axis labels by 45 degrees, and sets the labels for the x-axis and y-axis. The plot’s title is set to a string stored in data_label, and finally, the plot is displayed using plt.show().**

## Overall Conclusion

When analyzing the graphs, we noticed that the temperature in the cabbage fields varied between -4°C and 10°C, while the relative humidity fluctuated between 90% and 30%. Scientifically, it is known that most cabbage varieties (genus Brassica oleracea) can withstand short periods of frost, with minimum temperatures of -6°C, and some specific varieties can tolerate up to -10°C. However, prolonged exposure to temperatures below -5°C, for periods of 30 to 60 days, can be highly damaging, directly affecting plant development and crop quality. This is because these conditions can induce the process of early formation of flower stalks (called bolting), reducing the commercial value of the final product. Ideal cabbage growth occurs at an average daily temperature of around 17°C. According to studies, the temperature range considered ideal for cabbage development is 10°C to 24°C, with temperatures above 24°C slowing down development and increasing the risk of defects such as cracking and loss of firmness in cabbage heads. As for humidity, the ideal range for growing cabbage is between 60% and 90%. The graphs analyzed indicate that, for most of the time, relative humidity remained within suitable limits for the crop, especially at night, when levels tend to be higher. Studies show that humidity below 50% can increase transpiration and reduce the efficiency of water use by plants, while humidity above 90% for long periods favors the development of fungal diseases such as Alternaria and Peronospora brassicae. Based on this data, it is possible to conclude that the main focus should be on monitoring and controlling temperature, as it is the most critical factor for the health and performance of cabbage crops. To prevent damage, it is recommended to implement thermal control systems in greenhouses, such as heating on cold nights and adequate ventilation on hot days. In addition, automated monitoring systems can help maintain optimum temperature and humidity levels, thus ensuring a high-quality harvest. These recommendations are in line with modern agricultural research into the physiological needs of cabbage and with management strategies in regions with similar climatic variations.

## Scientific Poster

**Success Criteria:  The solution includes a poster summarizing the visual representations, model and analysis created. The poster includes a recommendation about healthy levels for Humidity, and Temperature(HL).**

![1  Temperature and humidity data collection Using the Arduino and the DHT 11 sensor, we measured the temperature and humidity  The laptop and Arduino are placed on the windowsill so that the DHT 1](https://github.com/user-attachments/assets/0f10426a-66bc-43ac-8a49-ddd443ccf419)

# Criteria D: Functionality

A 7 min video demonstrating the proposed solution with narration]

https://drive.google.com/drive/u/0/folders/1Vmt5poIBZQk42bdr8IFr16wJ1rlkdA-J

https://www.statology.org/quadratic-regression-python/
https://learnpython.com/blog/average-in-matplotlib/
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.rolling.html
