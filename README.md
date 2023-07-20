# Start page for [https://github.com/olvap80](https://github.com/olvap80)
All the stuff ready so far follows.

# [InstantRTOS](https://github.com/olvap80/InstantRTOS) - C++ 11, header-only minimalistic real time OS and handy utilities without dependencies
## Motivation
- RTOS to be quick to grasp
- RTOS to get rid of typecasts  and avoid boilerplate around simple things
- You do not pay for features you do not use (so suitable to work even on small embedded platforms, like Arduino, yep Arduino actually uses C++).
- Avoid third party dependencies
- Avoid complex build (allow add RTOS features by just including headers)
- Easy to configure (simple configuration rules on per file)
- Abstract out from platform specifics (so the same RTOS can run anywhere).
- Avoid the need of dynamic memory allocation (no new/delete, malloc/free).
- Make it easy to integrate with any platform!

## Features
- Lightweight and flexible scheduler operating on "callable things" can be runned on bare metal and even coexist with other RTOS (also you can have multiple schedulers)
- Compact delegates are used to tie all "callable things" together, glue/configure all the stuff (and are better than std::function for space and speed)) 
- Lightweight  stackless coroutines allow cooperative multitasking without burden of synchronization problems (they are also "callable things")
- Deterministic memory management (block pools and controlled object lifetime)
- Flexible options for timings
- Other handy utility stuff
  
On more details [please see here](https://olvap80.github.io/InstantRTOS/)


# [deferpp](https://github.com/olvap80/deferpp) - Go-lang like DEFER construction for C++ (execute code on scope exit)
[deferpp.h](https://github.com/olvap80/deferpp/blob/master/deferpp.h) - simple, lightweight, single header (header-only), quick and portable Go-like DEFER construction for C++11 and above, implemented in standard C++11 (but without involving std::function and without any dependencies at all!).

Usage:
```cpp
    {
        auto resource = AcquireSomeResource(parameters_here)
        DEFER{ FreeeThatResource(resource); };
        
        ... //work with that resource
    }
    //Note: code after DEFER is called when leaving scope due to any reason
    //      (one can reach scope end, issue return/break/continue or throw
    //       some exception, there is a guarantee such deferred code is called)
```
On more details [please see here](https://olvap80.github.io/deferpp/).
