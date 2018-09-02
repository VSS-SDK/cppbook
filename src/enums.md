# Enums

## C++
Domain/DurationType.h
```cpp
namespace vss {
    enum DurationType{
        TenMinutes = 0,
        UnlimitedMinutes = 1
    };

    std::string toDescription(DurationType);
    DurationType toDurationType(std::string);
}
```

Domain/EnvironmentType.h
```cpp
namespace vss {
    enum EnvironmentType{
        Simulation = 0,
        Real = 1
    };

    std::string toDescription(EnvironmentType);
    EnvironmentType toEnvironmentType(std::string);
}
```

Domain/FieldTransformationType.h
```cpp
namespace vss {
    enum FieldTransformationType{
        None = 0,
        Flip180Degrees = 1
    };

    std::string toDescription(FieldTransformationType);
    FieldTransformationType toFieldTransformationType(std::string);
}
```

Domain/MatchFinishType.h
```cpp
namespace vss {
    enum MatchFinishType{
        TenGoalsDifference = 0,
        TimeUp = 1
    };

    std::string toDescription(MatchFinishType);
    MatchFinishType toMatchFinishType(std::string);
}
```

Domain/SideAttackType.h
```cpp
namespace vss {
    enum SideAttackType{
        Left = 0,
        Right = 1
    };

    std::string toDescription(SideAttackType);
    SideAttackType toSideAttackType(std::string);
}
```

Domain/TimeExecutionType.h
```cpp
namespace vss {
    enum TimeExecutionType {
        Normal = 0,
        Fast = 1
    };

    std::string toDescription(TimeExecutionType);
    TimeExecutionType toTimeExecutionType(std::string);
}
```

Domain/TeamType.h
```cpp
namespace vss {
    enum TeamType{
        Yellow = 0,
        Blue = 1
    };

    std::string toDescription(TeamType);
    TeamType toTeamType(std::string);
}
```



## Rust
domain::team_type::TeamType
```rust
#[derive(Clone, Debug)]
pub enum TeamType {
    Yellow,
    Blue
}
```

use domain::field_transformation_type::FieldTransformationType
```rust
#[derive(Clone, Debug)]
pub enum FieldTransformationType {
    None,
    Flip180Degrees
}
```