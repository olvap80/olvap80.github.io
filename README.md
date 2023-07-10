# Start page for https://github.com/olvap80

## https://github.com/olvap80/InstantRTOS - header only hypermimimalistic real time OS and utilities without dependencies
- Whritten in C++, suitable to work even on small embedded platforms, like Arduino (yes Arduino actually uses C++!)
- No dependencies (even no standard headers needed) by default
- Only standard C++ (does not depend on any platform specifics)
- Each file contains usage sample, every API is documented with doxygen

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
