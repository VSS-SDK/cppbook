# Arquivos protos

Os arquivos protos carregam as definições de contrato entre os projetos. Caso exista necessidade de implementar 
a integração com o VSS-SDK em uma linguagem que não estenda C, é possível recriar as interfaces 
utilizando esses protocolos. 

State
```protobuf
package vss_state;

message Pose{
	required float x = 1;
	required float y = 2;
    optional float yaw = 3;
}

message Ball_State{
	required Pose pose = 1;
	optional Pose v_pose = 2;
}

message Robot_State{
	required Pose pose = 1;
	optional Pose v_pose = 2;
}

message Global_State{
	repeated Ball_State balls = 1;
	repeated Robot_State robots_yellow = 2;
	repeated Robot_State robots_blue = 3;
}
```

Command
```protobuf
package vss_command;

message Robot_Command{
	required float left_vel = 1;
	required float right_vel = 2;
}

message Global_Commands{
	repeated Robot_Command robot_commands = 1;
}
```

Debug
```protobuf
package vss_debug;

message Pose{
	required float x = 1;
	required float y = 2;
	optional float yaw = 3;
}

message Path{
	repeated Pose poses = 1;
}

message Global_Debug{
	repeated Pose step_poses = 1;
	repeated Pose final_poses = 2;
	repeated Path paths = 3;
}
```

Control
```protobuf
package vss_control;

message Pose{
	required float x = 1;
	required float y = 2;
	optional float yaw = 3;
}

message User_Control{
	optional bool paused = 1;
	optional Pose new_ball_pose = 2;
	repeated Pose new_robots_blue_pose = 3;
	repeated Pose new_robots_yellow_pose = 4;
}
```