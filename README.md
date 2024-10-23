# Cache memory in Logisim
This project consists of recreating a Cache Memory on the [Logisim](http://www.cburch.com/logisim/) simulation software. 
Thanks to Logisim, it allows an educational and detailed way to understand the internal functioning of a cache memory, 
and helps understanding its uses as the temporary and fast memory data between the processor and the RAM.
![Global representation of the architecture using cache](images/global_architecture.png)

# Technical specification
- The cache is of type 2-ways set associative, with write-back write policy and LRU (Least Recently Used) replacement policy.
- For sake of simplicity, the cache and the main memory can only handle 32 bits words, even though the addressable cell is about 8 bit. The memories are realigned in 4 Bytes.
- The response time of the cache is 1 cycle if the request hits, and many cycles otherwise. The read and write time of the main memory (RAM) is 10 cycles for one 32 bits word.
- The protocol Request/Busy (also known as Ready/Valid interface) was used to overcome the synchronization problem of communication between the CPU and the cache, or the chache and RAM.

More information is available in the project proposal [PDF](https://github.com/kara-abdelaziz/Cache-Memory-in-logisim/blob/main/side-project.pdf).

# Structural properties
![cache structure](images/Cache_structure.png)

# Logisim implementation
Maybe you will need to [download](https://github.com/kara-abdelaziz/Cache-Memory-in-logisim/blob/main/images/Cache_logisim_screenshot.png) the image to be able to zoom.
![cache logsim implementation](images/Cache_logisim_screenshot.png)

# FSM controllers
Three embedded controllers were used to ensure some sequential jobs needed for the proper working of the cache. The 3 controllers can be seen in the Logisim implementation image above. They are as follows, **Cache Controller** and its finite state machine, it is shown in the image below. The study of the finite state machine is registred in this [file](https://github.com/kara-abdelaziz/Cache-Memory-in-logisim/blob/main/FSM%20study/Controller%20SFM%20study.pdf).
![Cache controller](images/Cache_Controller_SM.png)

And the **Line Loader** and the **Line Strorer** which their finite state machine is described in the image below, they are responsible for loading a line from memory to the cache, and storing a line from cache to memory respectively. Those two controllers share practically the same finite state machine with small differences in their outputs. The study of their finite state machine is registred in this [file](https://github.com/kara-abdelaziz/Cache-Memory-in-logisim/blob/main/FSM%20study/Load-Store%20SFM%20study.pdf). 
![Line loader and storer controller](images/Line_Loader_Strorer_FSM.png)

# Files and directories description
1. Cache.circ : The main Logisim file, containing the whole circuit in one file.
2. side-project.pdf : This project was initially a side-project in a college computer architecture course. This file contains many details related to the design of the Cache.
3. README.md : This ream me text.
4. some addresses to test.txt : A text file containing some addresses tested with the Cache
5. side-project (pdf latex file) : side-project.pdf was generated using [Latex](https://en.wikipedia.org/wiki/LaTeX) text editor, all the generated files are stored in this directory.
6. FSM study : This directory contains many resources related to the study of the finite state machines mentioned above. Files related to the study of the two FSM are stored in this directory.
7. FSM study/Controller SFM study.pdf : A PDF containing the study process when designing the Cache Controller circuit.
8. FSM study/Load-Store SFM study.pdf : A PDF containing the study process when designing the Line Loader and the Line Storer circuits. They are practically similar, except for some minor changes in their outputs.
9. images : A directory containing all the images used in this README text.
   







