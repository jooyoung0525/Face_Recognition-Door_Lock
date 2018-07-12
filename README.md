# *WooJoo's* *Face_Recognition-Door_Lock*

**- Edison_Program(During Summer_Vacation)** **:** **Incheon_University,Electronic_Engineering**

----------------------------------------------------------------------------------------------------------------------------------------

## 1. Abstract

With the development of technology, door lock technology is gradually developing. There are various types of digital door locks to biometric door locks. As door lock technology develops, it is difficult to find a place that does not use door locks. 

Door locks are mainly used at the front door of a home, but we investigated the inconveniences of the door locks at the company doorway felt by the employees as the target company. Therefore, we designed the face recognition door lock which can solve the disadvantages of the door lock that office workers think. 

Our door locks were made using Raspberry Pi, Pi camera, Open CV, and APP Inventor. The difference from other door locks is that the door is opened only by face recognition during the day and double security by app and face recognition at night.

----------------------------------------------------------------------------------------------------------------------------------------

## 2. Introduce & Motivation
 
 office workers or researchers, They feel a lot of inconveniences in the entrance digital door lock of the lab or office. Because the doors are always locked when you leave the lab or office for a short period of time. So If the door is locked, it becomes inconvenient to have a password or fingerprint recognition every time you enter the office again. Because of this inconvenience, people are opening the office door. But if you continue to open the door, energy is wasted and peddler can visit. If you visit a lot of people, office people may feel psychologically uneasy about security. Therefore, in order to solve the problems of company doors, we made face recognition door locks targeting companies. The advantage of face recognition door lock is that it is possible to open the door lock without using the hand, and it is possible to solve the inconvenience of fingerprint recognition or password input every time of frequent entrance and exit. 
Also, if you use a camera with good performance, you can open the door quickly because you can recognize the face from a distance. The company is the our target so, our door locks can be secured by dividing the time between day and night. Because there are always people in the office during the day, primary security is safe. In addition, since employees are frequent in the daytime, the entrance is controlled only by face recognition in order to avoid the inconvenience of fingerprint recognition or password authentication. At night, because there is no one in the office and security is very important.
so, we are used double-security by appending an employee number login APP to the door lock.

---------------------------------------------------------------------------------------------------------------------------------------


## 3. Disadvantages of existing door locks




**● Digital Door Lock:**


*1. If you can not use both hands, it is difficult to press the button.*

*2. It is very easy to find your password, so you are always exposed to the risk of crime.*

*3. It is possible to give a hint when a certain button is worn or dirty because of long use.*




**● Fingerprint Door Lock:**


*1. Easy to copy fingerprints.*

*2. The fingerprint recognition rate drops due to palmar hyperhidrosis, water in your hand, or long-term use.*

*3. If you put gloves on your hands during winter or you have a lot of luggage in your hand, you may feel uncomfortable with fingerprint recognition.*





**● Existing face recognition door lock:**


*1.People with similar faces or photographs can open the door. So, Security is weak.*

*2. The price is very expensive. (About 2 million won)*

--------------------------------------------------------------------------------------------------------------------------------------


## 4. A difficult point


Face recognition is vulnerable security if you can not compensate this problems because it can be face recognition only with photo.
Many ideas came out to secure these weaknesses. Among them, we set boundary value for recognition rate when we perform face recognition. The threshold was set at 45% accuracy and the door lock was set to open only when the threshold was exceeded. We also created an app for double security. The app logs in with an employee number and sets face recognition door locks to work only when the login is successful. The process of collecting data for accurate face recognition took a long time and was difficult. We also had to control the app, raspberry pie, and door lock so there was a lot of trial and error in connecting software and hardware.

--------------------------------------------------------------------------------------------------------------------------------------


## 4. Used tools

**▶ SoftWare (SW)**

*- APP_Inventor*

*- Open CV*

*- PI camera*



**▶ HardWare (HW)**

*- Door Lock*

*- Raspberry PI*

*- Relay Module*

*- PI camera*

------------------------------------------------------------------------------------------------------------------------------------


## 5. How to make





------------------------------------------------------------------------------------------------------------------------------------


## 6. Result

At the time when employees go to the office (9:00 AM~18:00 PM), facial recognition can be used to control door access, which eliminates the inconvenience of passwords and fingerprint recognition for employees entering and exiting. Also, it is possible to control the entrance of peddler because it is secured by face recognition of employees. Security is important for employees when they leave the office (18:00 PM - 9:00 AM), so double security is implemented. Double security allows only company employees to log in to an employee number from an app, and face recognition can open the door if the login is successful.


----------------------------------------------------------------------------------------------------------------------------------------


## 7. Video



---------------------------------------------------------------------------------------------------------------------------------------

## 8. Reference
