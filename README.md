# Livox LiDAR 仿真环境 (Gazebo + ROS Noetic)

## 启动方式

```bash
# 启动仿真环境（Gazebo + UAV + RViz）
roslaunch livox_laser_simulation test_pattern.launch
```

## 文件结构

```
livox_laser_simulation/
├── launch/
│   └── test_pattern.launch
├── models/
│   └── sensors_only/
│       └── model.sdf
├── worlds/
│   └── test_livox.world
├── rviz/
│   └── test_pattern.rviz
└── README.md
```

## 功能特性

- ✅ **复杂障碍物环境**：包含圆柱、立方体、球体等多种障碍物
- ✅ **可配置 LiDAR 参数**：支持修改扫描范围、角度、分辨率等
- ✅ **RViz 可视化**：实时显示点云数据

## 注意事项

1. **spawn_model 报错处理**

   - 原因：Gazebo 中已存在同名模型 `iris_demo`


2. **LiDAR 参数调整**

   - 扫描范围：修改 `model.sdf` 中的 `<range><min>` 和 `<range><max>`
   - 水平/垂直角度：调整 `<horizontal>/<vertical>` 的 `min_angle` 和 `max_angle`
   - 分辨率：修改 `<samples>` 数量和 `<resolution>` 值

3. **障碍物检测优化**

   - 确保障碍物高度在 LiDAR 扫描范围内（调整 world 文件中的 `<pose>` z值）
   - 检查障碍物碰撞体积与视觉体积是否匹配


## 扩展使用

- 添加更多障碍物：在 `.world` 中修改模型定义
- 修改 UAV 起始位置：调整 launch 文件中的 `x, y, z` 参数
