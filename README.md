# Start page for [https://github.com/olvap80](https://github.com/olvap80)
All the stuff ready so far follows.

# [InstantRTOS](https://github.com/olvap80/InstantRTOS) - header-only minimalistic real time OS and handy utilities without dependencies
## Benefits
- Written in C++ 11, suitable to work even on small embedded platforms, like Arduino (yes Arduino actually uses C++! and yes, it is possible to write RTOS in C++).
- No dependencies (even no standard headers needed) by default.
- Only standard C++ (does not depend on any platform specifics).
- Dynamic memory is not required ("heavy" new/delete, malloc/free are not required).
- Each file contains usage samples, every API is documented with doxygen.
- Easy to integrate with any platform (see samples in corresponding files!)
- You can take away parts you need (like efficient Delegates and Coroutines) and use them separately without RTOS.

On more details [please see here](https://olvap80.github.io/InstantRTOS/)

## Features
### General utility headers

- [InstantDelegate.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantDelegate.h) - Fast deterministic delegates for invoking callbacks, suitable for real time operation (no heap allocation at all)

- [InstantCoroutine.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantCoroutine.h) - Simple minimalistic coroutines, suitable for all various platforms (like Arduino!) for the case when native C++ coroutines are too heavyweight (or when co_yield and stuff does not work)). Works starting from C++11 (so this can be considered as a nice coroutine implementation for Arduino, as Arduino uses C++11 by default)). NOTE: Coroutine behaves as functor and is perfectly compatible with [InstantDelegate.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantDelegate.h) (one can resume coroutines using [delegates](https://github.com/olvap80/InstantRTOS/blob/main/InstantDelegate.h), also [InstantScheduler.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantScheduler.h) can be used to schedule coroutines)

### Timing, intervals and scheduling

- [InstantScheduler.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantScheduler.h) - The simplest possible portable scheduler suitable for embedded platforms like Arduino (actually only standard C++ is required).

- [InstantTimer.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantTimer.h) - Simple timing classes to track timings in platform independent way (this is the most "primitive" and "basic" approach, use it only when [InstantScheduler.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantScheduler.h) does not fit due to some reason)

### Memory and queueing

- InstantMemory.h (TODO) - Simple deterministic memory management utilities suitable for real time can be used for fast and deterministic memory allocations on Arduino and similar platforms.

- InstantQueue.h (in progress) - Simple deterministic queues suitable for real time TBD.

### Other handy utility stuff

- [InstantDebounce.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantDebounce.h) (in progress) - General debouncing

- InstantSignals.h (in progress) - Handle hardware signals being mapped to memory


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
On more details [please see here](https://github.com/olvap80/deferpp/edit/master/README.md).
