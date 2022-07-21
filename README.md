## iotSprinkler

Summary: Microcontroller based sprinkler controller with HTTP server interface. Will allow single user connection on local network to device. Change irragation schedule or manually control watering. Smart watering mode will utilize weather data to automatically determine optimum watering amount. SD card for storing user preferences and logging basic system and weather data. 

Hardware: Planning on using the Nordic nrf52840 (has built in WiFi and bluetooth capability)

Top Level Flowchart on planned pages (starting simple):
```mermaid
graph TD
    A(iotSprinkler uC) --> |HTTP Server| B(Authentication Page)
    B -->|POST| C(Login Credentials)
    C -->D{Is Valid Credentials?}
    D -->|Yes| E[Default Page]
    D -->|No| F[Login Failure - add timeout?]
    F -->|show login failure msg| B 
    E -->G{GET}
    E -->H{POST}
    G-->I(Status and History)
    G-->J(Settings)
    G-->K(Schedule)
    H-->L(Settings)
    H-->Z(Schedule)
```
