# Start page for [https://github.com/olvap80](https://github.com/olvap80)

## [InstantRTOS](https://github.com/olvap80/InstantRTOS) - header-only mimimalistic real time OS and handy utilities without dependencies
- Written in C++ 11, suitable to work even on small embedded platforms, like Arduino (yes Arduino actually uses C++! and yes, it it possible to write RTOS in C++)
- No dependencies (even no standard headers needed) by default
- Only standard C++ (does not depend on any platform specifics)
- Each file contains usage sample, every API is documented with doxygen
- Easy to integrate with any platform (see samples in corresponding files!)

### General utility headers

- [InstantDelegate.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantDelegate.h) - Fast deterministic delegates for invoking callbacks, suitable for real time operation (no heap allocation at all)

- [InstantCoroutine.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantCoroutine.h) - Simple minimalistic coroutines suitable for all various platforms (like Arduino!) for the case when native C++ coroutines are too heavyweight (or when co_yield and stuff does not work)

### Timing, intervals and scheduling

- [InstantTimer.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantTimer.h) - Simple timing classes to track timings in platform independent way

- [InstantScheduler.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantScheduler.h) - The simplest possible portable scheduler suitable for embedded platforms like Arduino (actually only standard C++ is required)

### Memory and queueing

- InstantMemory.h - Simple deterministic memory management utilities suitable for real time can be used for dynamic memory allocations on Arduino and similar platform

- InstantQueue.h (in progress) - Simple deterministic queues suitable for real time can be used for dynamic memory allocations on Arduino and similar platforms.

### Other handy utility stuff

- [InstantDebounce.h](https://github.com/olvap80/InstantRTOS/blob/main/InstantDebounce.h) (in progress) - General debouncing

- InstantSignals.h (in progress) - Handle hardware signals being mapped to memory


## [deferpp](https://github.com/olvap80/deferpp) - Go-lang like DEFER construction for C++ (execute code on scope exit)
[deferpp.h](https://github.com/olvap80/deferpp/blob/master/deferpp.h) Simple, lightweight, single header only, quick and portable Go-like DEFER construction for C++11 and above, implemented in standard C++11 (but without involving std::function and without any dependencies at all!).
