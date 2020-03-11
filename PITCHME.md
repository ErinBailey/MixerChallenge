## Overview
- User provides n number of *unused* addresses via CLI
  - Error occurs if address is not unused
- User is prompted to send their coins to a randomly generated address (UUID)
- The program will poll the Jobcoin API to verify that the UUID address has received coins based on transaction length

---

## Overview II

- Coins are instantly deposited from the UUID address to the house account
- The house account distributes the coins to the addresses provided by the user at random intervals (30 seconds or less)
- User is notified as the coins are being deposited, and how long the deposit will be delayed

---

## Note:

The deposit time from the house account is a key part of the mixing process. By delaying the time in random intervals, it makes it more difficult for the user's original address to be traced back via timestamp. Ideally, a delay of anywhere between 1 hour and 3 days is what I would choose to implement in a production version.

---
## Architecture

- REST API
  - Uniform Interface
  - Client-Server
  - Stateless
  - Cacheable *
  - Layered System
  - Code on Demand *

---

## Architecture II

- Model - Providing the business logic in mixerlib
- View - Jobcoin GUI/ also the CLI user input 
- Controller - Handling the API calls in clientlib

---

## Pros
- Tests - go test covereage library
- Clear error messages
- Edge cases considered and/or documented
- Keeping it non-custodial

---

## Concerns
- Local development and early termination
- Current implementation is asynchronous

--- 

## Future Tweaks
- Webhooks instead of polling
- Host the application on a highly-available remote arechitecture 
- Depending on call volume, implement a queueing system
- Locking down addresses
- Synchronous go routines


