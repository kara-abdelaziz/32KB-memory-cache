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
Three embedded controllers were used to ensure some sequential jobs needed for the proper working of the cache. The 3 controllers can be seen in the Logisim implementation image above. They are as follows, **Cache Controller** and its finite state machine, it is shown in the image below.
![Cache controller](images/Cache_Controller_SM.png)
And the **Line Loader** and the **Line Strorer** which their finite state machine is described in the image below, they are responsible for loading a line from memory to the cache, and storing a line from cache to memory respectively. Those two controllers share practically the same finite state machine with small differences in their outputs.
![Line loader and storer controller](images/Line_Loader_Strorer_FSM.png)



