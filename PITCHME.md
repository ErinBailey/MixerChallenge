# Architecture

- REST API - 6 architectural principals
  - Uniform Interface
  - Client-Server
  - Stateless
  - Cacheable *
  - Layered System
  - Code on Demand *

---

# Architecture II
- MVC
  - Model - Providing the business logic in mixerlib
  - View - Jobcoin GUI/ also the CLI user input 
  - Controller - Handling the API calls in clientlib

---

# Pros
- Tests - go test covereage library
- Clear error messages
- Edge cases considered and/or documented
- Keeping it non-custodial

---

# Concerns
- Local development and early termination
- Current implementation is asynchronous

--- 

# Future Tweaks
- Webhooks instead of polling
- Host the application on a highly-available remote arechitecture 
- Depending on call volume, implement a queueing system
- Locking down addresses
- Synchronous go routines


