# pipes

## 

### Challenges integration

- Nuance of each technology
- Error handling
- Ordering
- Target considerations
  - Authentication
  - retries
  - rate control
- Performance testing
- Deployment
- Operations and monitoring

### The cost of integrations

- 多くのデベロッパーリソースが必要だった

### Introducing Amazon EventBridge Pipes

- Features / capabilities
  - Filter events
  - Batch events
- Benefits
  - Write less integration code
  - Save cost

### Event bus との違いは？

- BUS
  - Many publishers to many consumers
  - 1 - 1

### Qait, this all souds familiar..

- Pipes は　

### Use case

- case 1
  - SQS -> pipe -> Step Functions
- case 2
- case 3
  - kafra -> Filters
- case 4
- DDB strems -> Pipe -> Bis with Rule -> AWS Resource

### Demo

- 