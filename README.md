# crdc-datahub-starter-kit
This repo links all "ESSENTIAL" github repositories that used for building CRDC Datahub
The repositories as a submodule here are the core part of mtp programming ecosystem which covers  backend, front-end and etc. 

<br>

## Repos

1. AuthN  --  authentication ,  API authenticated (node.js)
2. AuthZ -- authorization, API getMyUser(node.js)
3. doc  -- documentation 
4. ui --- frontend.  (React)


## System diagram

```mermaid
graph TD
    A[Front-end] -->|Requests NIH login page| B[NIH login page]
    B -->|Returns code| A
    A -->|Calls API authenticated | C[AuthN Service]
    C -->|Create a Session | C
    A -->|Calls getMyUser| E[AuthZ Service]
    E -->|Gets user info| D[MonogoDb]
    A -->|Calls Graphql APIs | F[Backend Service]
    F -->|Fetches GUI content| D[MonogoDb]
    C --> |Fetches data | D
```
