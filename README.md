# Start page for [https://github.com/olvap80](https://github.com/olvap80)
All the stuff ready so far follows.

# [InstantRTOS](https://github.com/olvap80/InstantRTOS) - C++ 11, header-only minimalistic real time OS and handy utilities without dependencies
## Motivation
- RTOS to be quick and easy to grasp!
- RTOS to get rid of all those typecasts and to avoid boilerplate around simple things.
- You do not pay for those features you do not use (so InstantRTOS is suitable to work even on very small embedded platforms, like Arduino... yep Arduino actually uses C++).
- Avoid third party dependencies.
- Avoid complex build (allow adding RTOS features by just including headers - natural modularity).
- Easy to configure (simple configuration rules on per file basis), InstantRTOS is modular and allows developers to choose only the components they need for their application. 
- Portability: abstract out from platform specifics (so the same lightweight RTOS can run anywhere, on various microcontrollers and microprocessors, with minimal or no changes to the application code).
- Fast response: lightweight RTOS provides deterministic and predictable performance, ensuring that tasks meet their deadlines and events are handled promptly. 
- Avoid the need of dynamic memory allocation (no new/delete, no malloc/free, you can use then if you like, but do not have to do this)).
- Make it easy to integrate with any new platform! Platform specifics are introduced only if they are really used.
- Small footprint: InstantRTOS occupies minimal memory space, both in terms of code size and data structures.

## Design features of InstantRTOS
- InstantRTOS is built around "callable things" (functors) concept.
- Compact [delegates](https://github.com/olvap80/InstantRTOS/blob/main/InstantDelegate.h) are used to tie all "callable things" together, glue/configure all the stuff (and are better than std::function by space and speed))
- Lightweight and flexible [scheduler](https://github.com/olvap80/InstantRTOS/blob/main/InstantScheduler.h) operates on "callable things". Scheduler is platform independent and can be runned anywhere, and even can coexist with other RTOS (also you can have multiple schedulers and invent your own strategies on how to distribute CPU time between them).
- Lightweight stackless [coroutines](https://github.com/olvap80/InstantRTOS/blob/main/InstantCoroutine.h) are also "callable things" and allow cooperative multitasking without the burden of synchronization problems.
- Deterministic memory management ([block pools and controlled object lifetime](https://github.com/olvap80/InstantRTOS/blob/main/InstantMemory.h)).
- Flexible options for [timings](https://github.com/olvap80/InstantRTOS#timing-intervals-and-scheduling).
- Other handy [utility stuff](https://github.com/olvap80/InstantRTOS#other-handy-utility-stuff)
- No "glabal state" at all, so that you can have multiple InstantRTOS shedulers in the same address space (and even run them in parallel and/or coexist with other RTOS) 
  
On more details [please see here](https://olvap80.github.io/InstantRTOS/).


# [deferpp](https://github.com/olvap80/deferpp) - Go-lang like DEFER construction for C++ (execute code on scope exit)
[deferpp.h](https://github.com/olvap80/deferpp/blob/master/deferpp.h) - simple, lightweight, single header (header-only), quick and portable Go-like DEFER construction for C++11 and above, implemented in standard C++11 (but without involving "heavy" std::function and without any dependencies at all!). Get rid of manual RAII wrapper classes, the golang-style "defer" in C++ makes it easy to manage resources! 

Usage sample for "defer from Go in pure C++":
```cpp
    {
        auto resource = AcquireSomeResource(parameters_here)
        DEFER{ FreeeThatResource(resource); };
        
        ... //work with that resource
    }
    //Note: code block after DEFER is called once leaving scope due to any reason
    //      (one can reach scope end, issue return/break/continue or throw
    //       some exception, there is a guarantee such deferred code is called)
```
On more details [please see here](https://olvap80.github.io/deferpp/).
