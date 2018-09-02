# Interfaces de comunicação

Interfaces/IStateReceiver.h, Communications/StateReceiver.h
```cpp
namespace vss{
    class StateReceiver : public IStateReceiver {
    public:
        StateReceiver();

        void createSocket(Address) override;
        void createSocket() override;
        State receiveState(FieldTransformationType) override;
    };
}
```

Interfaces/IStateSender.h, Communications/StateSender.h
```cpp
namespace vss{
    class StateSender : public IStateSender  {
    public:
        StateSender();

        void createSocket(Address) override;
        void createSocket() override;
        void sendState(State) override;
    };
}
```

Interfaces/ICommandSender.h, Communications/CommandSender.h
```cpp
namespace vss {
    class CommandSender : public ICommandSender {
    public:
        CommandSender();

        void createSocket(Address) override;
        void createSocket(TeamType) override;
        void sendCommand(Command) override;
    };
}
```

Interfaces/IDebugReceiver.h, Communications/DebugReceiver.h
```cpp
namespace vss {
    class DebugReceiver : public IDebugReceiver {
    public:
        DebugReceiver();

        void createSocket(Address) override;
        void createSocket(TeamType) override;
        Debug receiveDebug() override;
    };
}
```

Interfaces/IDebugSender.h, Communications/DebugSender.h
```cpp
namespace vss {
    class DebugSender : public IDebugSender {
    public:
        DebugSender();

        void createSocket(Address) override;
        void createSocket(TeamType) override;
        void sendDebug(Debug) override;
    };
}
```

Interfaces/IControlReceiver.h, Communications/ControlReceiver.h
```cpp
namespace vss {
    class ControlReceiver : public IControlReceiver {
    public:
        ControlReceiver();

        void createSocket(Address) override;
        void createSocket() override;
        Control receiveControl() override;
    };
}
```

Interfaces/IControlSender.h, Communications/ControlSender.h
```cpp
namespace vss {
    class ControlSender : public IControlSender {
    public:
        ControlSender();

        void createSocket(Address) override;
        void createSocket() override;
        void sendControl(Control) override;
    };
}
```