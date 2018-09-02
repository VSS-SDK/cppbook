# Exemplos

 Exemplos de estratégias que obtém estados do VSS-Vision e VSS-Simulator, enviam comandos para 
 o VSS-Simulator e enviam informações de debug para o VSS-Viewer. 
 
## C++ [![GitHub stars](https://img.shields.io/github/contributors/VSS-SDK/VSS-SampleCpp.svg?style=social&label=Contributors)](https://github.com/VSS-SDK/VSS-SampleCpp)

```cpp
#include <StateReceiver.h>
#include <CommandSender.h>
#include <DebugSender.h>

using namespace vss;

int main(int argc, char** argv){
    IStateReceiver *stateReceiver = new StateReceiver();
    ICommandSender *commandSender = new CommandSender();
    IDebugSender *debugSender = new DebugSender();

    stateReceiver->createSocket();
    commandSender->createSocket(TeamType::Yellow);
    debugSender->createSocket(TeamType::Yellow);

    while(true){
        State state;
        Command command;
        Debug debug;
        
        state = stateReceiver->receiveState(FieldTransformationType::None);
        commandSender->sendCommand(command);
        debugSender->sendDebug(debug);
    }

    return 0;
}
```

## Rust [![GitHub stars](https://img.shields.io/github/contributors/VSS-SDK/VSS-SampleRust.svg?style=social&label=Contributors)](https://github.com/VSS-SDK/VSS-SampleRust)

```rust
extern crate vss_core;

use vss_core::communications::command_sender::CommandSender;
use vss_core::communications::state_receiver::StateReceiver;
use vss_core::communications::debug_sender::DebugSender;
use vss_core::domain::field_transaformation_type::FieldTransformationType;
use vss_core::domain::team_type::TeamType;
use vss_core::domain::command::Command;
use vss_core::domain::debug::Debug;

fn main() {
    let mut command_sender = CommandSender::new();
    let mut debug_sender = DebugSender::new();
    let mut state_receiver = StateReceiver::new();

    command_sender.create_socket(TeamType::Yellow);
    debug_sender.create_socket(TeamType::Yellow);
    state_receiver.create_socket();

    loop {
        let _ = state_receiver.receive_state(FieldTransformationType::None);
        command_sender.send_command(Command::new());
        debug_sender.send_debug(Debug::new())
    }
}
```