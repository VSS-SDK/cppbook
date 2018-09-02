# Modelos básicos

Domain/Point.h
```cpp
namespace vss {
    class Point {
    public:
        Point();
        Point(float x, float y);

        friend std::ostream& operator<<(std::ostream& os, const Point& point);

        float x;
        float y;
    };
}
```

Domain/Pose.h
```cpp
namespace vss {
    class Pose : public Point {
    public:
        Pose();
        Pose(float x, float y, float angle);

        friend std::ostream& operator<<(std::ostream& os, const Pose& pose);

        float angle;
    };
}
```

Domain/Ball.h
```cpp
namespace vss {
    class Ball : public Point {
    public:
        Ball();
        Ball(float x, float y, float speedX, float speedY);

        friend std::ostream& operator<<(std::ostream& os, const Ball& ball);

        float speedX;
        float speedY;
    };
}
```

Domain/Robot.h
```cpp
amespace vss {
    class Robot : public Pose {
    public:
        Robot();
        Robot(float x, float y, float angle, float speedX, float speedY, float speedAngle);

        friend std::ostream& operator<<(std::ostream& os, const Robot& robot);

        float speedX;
        float speedY;
        float speedAngle;
    };
}
```

Domain/Path.h
```cpp
namespace vss {
    class Path {
    public:
        Path();
        Path(std::vector<Point> points);

        friend std::ostream& operator<<(std::ostream& os, const Path& path);

        std::vector<Point> points;
    };
}
```

WheelsCommand.h
```cpp
namespace vss {
    class WheelsCommand {
    public:
        WheelsCommand();
        WheelsCommand(int id, float leftVel, float rightVel);

        friend std::ostream& operator<<(std::ostream& os, const WheelsCommand& wheelsCommand);

        int id;
        float leftVel;
        float rightVel;
    };
}
```