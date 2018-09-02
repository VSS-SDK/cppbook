# Obtendo estados

```cpp
#include "Interfaces/IStateReceiver.h"
#include "Communications/StateReceiver.h"
#include "Domain/State.h"

using namespace vss;

int main(int argc, char** argv){
    IStateReceiver *stateReceiver = new StateReceiver();
    stateReceiver->createSocket();

    while(true){
        State state = stateReceiver->receiveState(FieldTransformationType::None);
    }

    return 0;
}
```