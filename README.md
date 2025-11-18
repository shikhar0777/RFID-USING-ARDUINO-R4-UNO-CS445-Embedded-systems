# RFID-USING-ARDUINO-R4-UNO-CS445-Embedded-systems
PROJECT SMART R4

Smart RFID-Based Attendance Monitoring System Using; Arduino UNO R4 WiFi
Course: Embedded Systems  CS 445 (Bachelor Level)
 Instructor: Dr. Ali Al-Sinayyid
 Student: Shikhar Pandey
 Department of Computer Science
 West Virginia State University

Abstract
This research project proposes the development of a smart, contactless RFID-based attendance monitoring system utilizing the Arduino UNO R4 WiFi and the MFRC522 RFID module. The system is designed to address the limitations of traditional manual attendance processes, including errors, inefficiency, and lack of security. In the proposed design, each authorized user is assigned a unique RFID card. When the card is tapped, the system reads the UID, verifies access permissions, and automatically logs the attendance with a precise timestamp. Unauthorized card scans are immediately rejected and can trigger notifications for enhanced security.The Arduino UNO R4 WiFi enables wireless communication for cloud-based logging or local database integration, allowing attendance data to be seamlessly exported into structured formats such as Excel sheets. This project demonstrates an embedded system that integrates hardware interfacing, real-time data processing, and IoT-based communication. The resulting solution provides a scalable, low-cost, and efficient approach suitable for classrooms, offices, and restricted zones requiring secure access control.
Keywords
RFID, MFRC522, Arduino UNO R4 WiFi, Attendance System, IoT Security, Embedded Systems, Automation, Access Control, Wireless Logging, Real-Time Monitoring.

1. Introduction
Attendance tracking is a critical requirement in academic institutions, offices, and controlled-access environments. Traditionally, attendance has been recorded manually using paper-based sheet signing, rollcalling, or analog registers. These conventional methods suffer from several significant limitations: they are time-consuming, prone to human error[1], vulnerable to manipulation, and inefficient for large groups. Issues such as proxy attendance, inaccurate timestamps, misplaced registers, and delayed reporting frequently undermine the reliability of the process. As institutions expand and adopt modern digital practices, these outdated methods fail to meet the demands for accuracy, speed, and security.

To address these challenges, a shift toward automated attendance monitoring systems has become essential. Over the past decade, technologies such as barcode scanners, biometric systems, and card-based access systems have been explored. However, many of these solutions either require expensive infrastructure, introduce privacy concerns (e.g., biometrics), or demand high maintenance. In contrast, Radio Frequency Identification (RFID) [2]  technology offers a low-cost, contactless, and durable alternative that simplifies user interaction while ensuring reliable identity verification.
This project proposes the design and implementation of a Smart RFID-Based Attendance System using the Arduino UNO R4 WiFi and the MFRC522 RFID reader. The system assigns each user a unique RFID card, which, when tapped near the reader, transmits its UID wirelessly for verification. The Arduino processes this UID to determine whether the card belongs to an authorized user. Valid scans are logged instantly with accurate timestamps, while invalid scans trigger rejection or security alerts. The integration of the WiFi-enabled [3]UNO R4 allows the system to store attendance data in cloud databases or export it to formats such as Excel for real-time monitoring and analysis.The proposed solution addresses the shortcomings of traditional attendance methods by providing automation, accuracy, contactless operation, enhanced security, and the capacity for remote monitoring. This project also demonstrates key embedded systems concepts including sensor integration, digital communication (SPI protocol), data logging, and IoT connectivity. Ultimately, the system offers a scalable model that can be deployed in classrooms, laboratories, offices, and secure entry points, making it a practical and modern alternative to manual attendance tracking.
2. Design and Modeling
2.1 System Design
The RFID-based Attendance Monitoring System was designed to provide a reliable, low-cost, and automated method for recording student or employee attendance. The design integrates an RFID reader module with a microcontroller platform to detect card identities, validate authorized users, and generate timestamped logs. The system emphasizes simplicity, scalability, and easy deployment in real-world environments.

The software for this RFID-based attendance system is developed using the Arduino Integrated Development Environment (Arduino IDE), which provides a simple platform for writing, compiling, and testing embedded code. The system relies on two essential libraries: the MFRC522 library, which enables communication between the Arduino UNO R4 WiFi and the RC522 RFID reader, and the SPI library, which supports the Serial Peripheral Interface protocol used by the RFID module. Together, these software components allow the microcontroller to read card UIDs, authenticate users, and generate precise attendance logs. The Arduino IDE also provides a serial monitor that assists in testing and debugging, making it possible to verify system behavior even without the physical hardware. This software setup ensures a structured, reliable, and fully programmable environment for implementing the system’s core functions.
  



2.2 Modeling and Moduling
In this system, modeling and moduling show how all the parts work together to record attendance using RFID cards. The system is divided into small modules, so each part does a specific job. This makes it easy to understand, test, and improve later.
The system consists of three main layers. The Input Layer uses the RC522 RFID reader to read each card’s unique ID and send it to the Arduino UNO R4 WiFi through jumper wires using the SPI connection. The Processing Layer is handled by the Arduino, which verifies the card ID, records attendance, and decides whether access is granted or denied. The Output Layer displays results on the Serial Monitor in the Arduino IDE, allowing testing even without hardware connected.


The system is organized into modules, each with a specific task. The RFID Reader Module reads the card ID and sends it to the Arduino. The Arduino Controller Module processes the ID, records attendance, and manages data. The Serial Output Module shows messages for testing. Jumper wires connect the modules electrically, and the Power Module provides the required 3.3V and 5V. This modular design makes the system easy to understand, test, and upgrade, for example by adding a display or WiFi notifications.



3. Data Flow
The data flow of the Smart RFID-Based Attendance System explains how information moves from the user’s RFID card to the final attendance record. The system captures, verifies, and logs attendance in a structured manner, ensuring accuracy and real-time monitoring.
When a user taps their RFID card on the RC522 reader, the card’s unique ID (UID) is read and sent to the Arduino UNO R4 WiFi through jumper wires using the SPI protocol. The Arduino acts as the processing layer, verifying whether the UID belongs to an authorized user. If the UID is valid, the system records the attendance with a timestamp. If invalid, the system rejects the scan, and a corresponding message is shown.The processed information is then sent to the Serial Monitor, which displays status messages such as “Access Granted” or “Access Denied.” Additionally, attendance data can be exported to Excel sheets or a cloud database for centralized storage and analysis. This flow ensures that data is captured, verified, and stored efficiently, allowing real-time monitoring and reducing errors compared to manual attendance systems.


The Level 0 Data Flow of the Smart RFID-Based Attendance System provides a high-level overview of the entire system. At this level, the system is viewed as a single process that interacts with external entities. When a user taps an RFID card, the system captures the unique ID and processes it to determine attendance. The processed information is then delivered to output destinations, which include the Serial Monitor for immediate feedback and optional cloud or Excel logging for centralized storage and future analysis. This level emphasizes the main data sources and destinations without detailing the internal modules.



The Level 1 Data Flow provides a more detailed view, breaking the system into functional modules. Here, the RFID Reader Module reads the card’s unique ID and transmits it to the Arduino Controller Module via SPI communication. The Arduino then verifies whether the UID belongs to an authorized user, records attendance, and generates a corresponding status message. The Serial Output Module displays the result, such as “Access Granted” or “Access Denied,” while the data can also be logged in Excel or a cloud database. Level 1 highlights the internal processing steps and the flow of data between modules, demonstrating how the system ensures accurate and real-time attendance tracking.


4) Actuators and Sensors
This project uses only a few basic components because the system is designed to read RFID cards and verify attendance through the Arduino IDE. The main sensing device is the RFID reader, and there are no actuators since no doors, motors, or alarms are being controlled.
Sensors Used
RFID Reader (MFRC522)
 This is the main sensor of the system[5]. It reads the unique ID (UID) from each RFID card or tag.
 Specs:


Frequency: 13.56 MHz


Communication: SPI


Operating Voltage: 3.3V


Reading Distance: 2–5 cm


Controller
Arduino UNO R4 WiFi
 Works as the processing unit. It receives the card ID from the RFID module[5], checks if the card is valid, and prints results on the Serial Monitor and this arduino have wifi embedded.


Supporting Components
Jumper Wires
 Used to connect the RFID module to the Arduino for power and data (SPI lines).


Since this version of the project focuses only on reading cards and showing results on the Serial Monitor, no actuators (such as motors, relays, or buzzers) are used.


5) Objectives
To create a basic RFID-based attendance system using Arduino UNO R4 WiFi and the RC522 RFID reader.


To accurately read and verify card IDs for marking valid attendance.


To make attendance more reliable and error-free compared to manual methods.


To help teachers or companies adopt a modern digital attendance process.


To store attendance data in an Excel-friendly format for easy tracking and record-keeping.

6. Testing
The testing phase ensures that the RFID-based attendance system works correctly before full deployment. Since the hardware was not fully connected during development, testing was performed in two levels: software testing and module-level validation.
Software Testing:
 The Arduino code was uploaded and tested using the Serial Monitor in the Arduino IDE. This allowed verification that the system could correctly read sample card IDs, compare them with stored authorized IDs, and display the appropriate output messages such as “Access Granted” or “Access Denied.” The logic for attendance recording, time stamping, and handling invalid cards was also tested by simulating card IDs directly in the code.
Module-Level Testing:
 Each module was checked individually to ensure expected behavior. The RFID RC522 module was validated using basic read-tests to confirm that the program could detect card UID format and respond properly. The Arduino UNO R4 WiFi board was tested to ensure the SPI communication functions worked and that the board successfully executed the attendance logic. Jumper wire connections and pin mapping were verified through code simulation and reference diagrams.
System Integration Check:
 Even without physical hardware available, the entire workflow was virtually tested by observing serial outputs. This ensured that when hardware is connected later, the system will operate as intended scanning a card, verifying identity, and recording attendance reliably.

7. Result
8. Conclusion 




REFRENCES 


[1] Ula, Mutammimul, et al. "A new model of the student attendance monitoring system using rfid technology." Journal of Physics: Conference Series. Vol. 1807. No. 1. IOP Publishing, 2021.

[2]Ajami S, Rajabzadeh A. Radio Frequency Identification (RFID) technology and patient safety. J Res Med Sci. 2013 Sep;18(9):809-13. PMID: 24381626; PMCID: PMC3872592.

[3]Durden, Garey C., and Larry V. Ellis. "The effects of attendance on student learning in principles of economics." The American Economic Review 85.2 (1995): 343-346.

[4]Alan, Muhamad Bagus Fikril, et al. “Design and Implementation of Photovoltaic Monitoring System Using Arduino UNO R4.” IEEE,2020

[5]Bolic, Miodrag, David Simplot-Ryl, and Ivan Stojmenovic, eds. "RFID systems: research trends and challenges." (2010).
