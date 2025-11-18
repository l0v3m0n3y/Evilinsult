# Evilinsult
api for evilinsult.com site for getting evil insult
# main
```cpp
#include "Evilinsult.h"
#include <iostream>

int main() {
   Evilinsult api;

    auto insult= api.generate_insult("en").then([](json::value result) {
        std::cout << "Search results: " << result.serialize() << std::endl;
    });
    insult.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
