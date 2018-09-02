# Modelos de comunicação

Domain/Address.h
```cpp
namespace vss {
    class Address {
    public:
        Address();
        Address(std::string ip, int port);

        friend std::ostream& operator<<(std::ostream& os, const Address& address);

        void setIp(std::string ip);
        void setPort(int port);

        std::string getIp();
        int getPort();

        std::string getFullAddress();

        std::string ip;
        int port;
    };
}
```

Domain/State.h
```cpp
namespace vss {
    class State {
    public:
        State();
        State(Ball ball, std::vector<Robot> teamBlue, std::vector<Robot> teamYellow);

        friend std::ostream& operator<<(std::ostream& os, const State& state);

        Ball ball;
        std::vector<Robot> teamBlue;
        std::vector<Robot> teamYellow;
    };
}
```

Domain/Command.h
```cpp
namespace vss {
    class Command {
    public:
        Command();
        Command(int id, std::vector<WheelsCommand> commands);

        friend std::ostream& operator<<(std::ostream& os, const Command& command);

        int id;
        std::vector<WheelsCommand> commands;
    };
}
```

Domain/Debug.h
```cpp
namespace vss {
    class Debug {
    public:
        Debug();
        Debug(std::vector<Point> stepPoints, std::vector<Pose> finalPoses, std::vector<Path> paths);

        friend std::ostream& operator<<(std::ostream& os, const Debug& debug);

        std::vector<Point> stepPoints;
        std::vector<Pose> finalPoses;
        std::vector<Path> paths;
    };
}
```

Domain/Control.h
```cpp
namespace vss {
    class Control {
    public:
        Control();
        Control(bool paused, Ball ball, std::vector<Robot> teamYellow, std::vector<Robot> teamBlue);

        friend std::ostream& operator<<(std::ostream& os, const Control& control);

        bool paused;
        Ball ball;
        std::vector<Robot> teamYellow;
        std::vector<Robot> teamBlue;
    };
}
```