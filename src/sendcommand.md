# Enviando comandos

```cpp
#include "Interfaces/ICommandSender.h"
#include "Communications/CommandSender.h"
#include "Domain/Command.h"

using namespace vss;

int main(int argc, char** argv){
    ICommandSender commandSender = new CommandSender();
    commandSender->createSocket(TeamType::Yellow);

    while(true){
        Command command;
        commandSender->sendCommand(command);
    }

    return 0;
}
```