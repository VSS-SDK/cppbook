# VSS-SampleCpp [![GitHub stars](https://img.shields.io/github/stars/VSS-SDK/VSS-SampleCpp.svg?style=social&label=Stars)](https://github.com/VSS-SDK/VSS-SampleCpp)

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)][gpl3]
[![Build Status](https://api.travis-ci.com/VSS-SDK/VSS-SampleCpp.svg?branch=master)][travis]

```cpp
#include <Communications/StateReceiver.h>
#include <Communications/CommandSender.h>
#include <Communications/DebugSender.h>
#include "cstdlib"

using namespace vss;

IStateReceiver *stateReceiver;
ICommandSender *commandSender;
IDebugSender *debugSender;

State state;


void send_commands();
void send_debug();

int main(int argc, char** argv){
    srand(time(NULL));

    stateReceiver = new StateReceiver();
    commandSender = new CommandSender();
    debugSender = new DebugSender();

    stateReceiver->createSocket();
    commandSender->createSocket(TeamType::Yellow);
    debugSender->createSocket(TeamType::Yellow);

    while(true){
        state = stateReceiver->receiveState(FieldTransformationType::None);
        send_commands();
        send_debug();
    }

    return 0;
}

void send_commands(){
    Command command;

    for(int i = 0 ; i < 3 ; i++){
        WheelsCommand wheelsCommand;

        wheelsCommand.leftVel = 10;
        wheelsCommand.rightVel = -10;

        command.commands.push_back(wheelsCommand);
    }

    commandSender->sendCommand(command);
}


void send_debug(){
    vss::Debug debug;

    for(unsigned int i = 0 ; i < 3 ; i++){
        vss::Point point;

        point.x = state.teamYellow[i].x - 10 + rand()%20;
        point.y = state.teamYellow[i].y - 10 + rand()%20;

        debug.stepPoints.push_back(point);
    }

    for(unsigned int i = 0 ; i < 3 ; i++){
        vss::Pose pose;

        pose.x = state.teamYellow[i].x - 10 + rand()%20;
        pose.y = state.teamYellow[i].y - 10 + rand()%20;
        pose.angle = state.teamYellow[i].y - 10 + rand()%20;

        debug.finalPoses.push_back(pose);
    }

    for(unsigned int i = 0 ; i < 3 ; i++){
        vss::Path path;
        vss::Point point_1;
        vss::Point point_2;

        point_1.x = state.teamYellow[i].x;
        point_1.y = state.teamYellow[i].y;

        point_2.x = state.ball.x - 10 + rand()%20;
        point_2.y = state.ball.y - 10 + rand()%20;

        path.points.push_back(point_1);
        path.points.push_back(point_2);
    }

    debugSender->sendDebug(debug);
}
```

[gpl3]: http://www.gnu.org/licenses/gpl-3.0/
[travis]: https://travis-ci.com/VSS-SDK/VSS-SampleCpp