Concurrency decouples what gets done from when it gets done (async?)

concurrency can sometimes improve performance but only when there is a lot of wait time

design of concurrent code can be differ a lot from single-thread design

**Keep concurrency-related code separate from other code**

**Severely limit the access of any data that may be shared**

### Algorithms for dealing with concurrent synchronizing
1) Producer - Consumer -> place items to be processed in a queue
2) Readers-Writers -> wait until there are no 'readers' before a 'writer' can contribute information
3) Dining Philosophers -> any one philosopher must have '2 forks' before being able to grab more spaghetti, ortherwise he must wait

