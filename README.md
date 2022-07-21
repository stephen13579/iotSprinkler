# iotSprinkler
Microcontroller based sprinkler controller with HTTP server interface

'''mermaid
graph TD
    A(iotSprinkler uC) --> |HTTP Server| B(Authintication Page)
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
'''
