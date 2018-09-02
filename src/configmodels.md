# Modelos de configuração

Domain/ExecutionConfig.h
```cpp
namespace vss {
    class ExecutionConfig {
    public:
        ExecutionConfig();

        friend std::ostream& operator<<(std::ostream& os, const ExecutionConfig& executionConfig);

        // Communications
        Address stateRecvAddr;
        Address stateSendAddr;

        Address cmdYellowRecvAddr;
        Address cmdYellowSendAddr;
        Address debugYellowRecvAddr;
        Address debugYellowSendAddr;

        Address cmdBlueRecvAddr;
        Address cmdBlueSendAddr;
        Address debugBlueRecvAddr;
        Address debugBlueSendAddr;

        Address ctrlRecvAddr;
        Address ctrlSendAddr;

        // Enums
        TeamType teamType;
        SideAttackType sideAttackType;
        TimeExecutionType timeExecutionType;
        EnvironmentType environmentType;
        DurationType durationType;
        MatchFinishType matchFinishType;

        // Others
        std::string teamInitialPositionPath;

        bool isValidConfiguration;
    };
}
```