# Interprete de configuração

Builders/StdinInterpreterBuilder.h
```cpp
namespace vss {
    class StdinInterpreterBuilder : public IStdinInterpreterBuilder {
    public:
        StdinInterpreterBuilder();

        IStdinInterpreter* buildInterpreter() override;

        IStdinInterpreterBuilder* onStateRecvAddr() override;
        IStdinInterpreterBuilder* onStateSendAddr() override;

        IStdinInterpreterBuilder* onYellowCmdRecvAddr() override;
        IStdinInterpreterBuilder* onYellowCmdSendAddr() override;
        IStdinInterpreterBuilder* onYellowDebugRecvAddr() override;
        IStdinInterpreterBuilder* onYellowDebugSendAddr() override;

        IStdinInterpreterBuilder* onBlueCmdRecvAddr() override;
        IStdinInterpreterBuilder* onBlueCmdSendAddr() override;
        IStdinInterpreterBuilder* onBlueDebugRecvAddr() override;
        IStdinInterpreterBuilder* onBlueDebugSendAddr() override;

        IStdinInterpreterBuilder* onCtrlRecvAddr() override;
        IStdinInterpreterBuilder* onCtrlSendAddr() override;

        IStdinInterpreterBuilder* onStatePort() override;
        IStdinInterpreterBuilder* onYellowCmdPort() override;
        IStdinInterpreterBuilder* onYellowDebugPort() override;
        IStdinInterpreterBuilder* onBlueCmdPort() override;
        IStdinInterpreterBuilder* onBlueDebugPort() override;
        IStdinInterpreterBuilder* onCtrlPort() override;

        IStdinInterpreterBuilder* onTeamType() override;
        IStdinInterpreterBuilder* onSideAttackType() override;
        IStdinInterpreterBuilder* onTimeExecutionType() override;
        IStdinInterpreterBuilder* onEnvironmentType() override;
        IStdinInterpreterBuilder* onDurationType() override;
        IStdinInterpreterBuilder* onMatchFinishType() override;

        IStdinInterpreterBuilder* onTeamInitialPositionPath() override;

    protected:
        IStdinInterpreter *stdinInterpreter;
    };
}
```

Interpreters/StdinInterpreter.h
```cpp
namespace vss {
    class StdinInterpreter : public IStdinInterpreter {
    public:
        StdinInterpreter();

        ExecutionConfig extractExecutionConfig(int argc, char **argv) override;

    protected:
        ExecutionConfig stdinConfiguration;

        boost::program_options::options_description buildOptions();
        void buildConfiguration(boost::program_options::variables_map);
    };
}
```