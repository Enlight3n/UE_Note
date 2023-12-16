
# 1. FPS游戏简介
FPS：First-person Shooter
```mermaid
graph LR
德军总部3D --> 毁灭战士
毁灭战士 --> 半条命
半条命 --> 反恐精英
```
# 2. FPS游戏基础框架

<table>  
<tr align="center">  
<td colspan=2,>Weapon</td>  
<td colspan=2>3C</td>  
<td colspan=2,>GamePlay</td>  
</tr>  
<tr align="center">  
<td colspan=6,>GamePlay</td>  
</tr>  
<tr align="center">  
<td colspan=3,>Game Core
</td>  
<td colspan=3>Third Party Library</td>  
</tr>  
<tr align="center">  
<td colspan=6,>Game Engine </td>  
</tr>  
<tr align="center">  
<td colspan=6,>Operating System </td>  
</tr>  
</table>

# 3. Weapon System

## FPS中常见的武器类型
- 按种类分：
步枪、狙击枪、手枪、手雷等
- 按装备位分
主武器、副武器、近战武器、投掷武器
- 按程序逻辑分
lnstantHit、Projectile等

## 关键基础组件
### 物理引擎
#### PhysX
- 属于NVIDA，现已开源，是UE4和Unitl的主要内置物理引擎，使用它的游戏非常多
#### Havok
- 老牌的商业引擎，代表作品包括：刺客信条，Doom Eternal，Monster Hunter World等
#### Bullet
- 广泛应用于游戏开发和电影制作中。Bullet也是AMD开放物理计划成员之一
### 弹道模型
#### 影响弹道的因素
- 主视角角度
- 后坐力
- 连发数
- 精准度
- 散发度
#### 后坐力与连发的关系
- 主弹道子弹射出方向=主视角角度+后坐力+精准度+散发度
- 后坐力、精准度、散发度与具体武器相关，通过配置参数与公式计算得出
- 举例一种散发度的公式：散发方向=随机数x散发x水平/垂直方向

# 4. 3C System
## Character
角色，具有一定的能力或行为，玩家可以进行扮演或观察

技术要点：
- 表现方面
- 逻辑方面
- 角色状态的设计与转换
- 细节问题

## Camera
相机，玩家通过它观察游戏世界，获得体验感和沉浸感

技术要点
- 渲染顺序
- FOV
- 碰撞盒位置的控制

 ## Control
 为玩家提供了不同的方式和不同的体验
 - 设备与手感
 - 手游适配问题
	- 同样代码，iOS与Android灵敏度不同
	- 不同Android手机，灵敏度不同
	- 部分Android手机灵敏度偏低
- 辅助瞄准
- 硬件功能
# 5. 其他技术点

## 网络同步
- 帧同步与状态同步
- Peeker's Advantage
## 反外挂
- 外挂分类
- 外挂原理
- 方法：
	- 服务器校验
	- 服务器数据下发
	- 客户端数据加密
	- 客户端动态检测

## 性能优化
### CPU优化
- 物理性能优化
- 动画优化
- 流程逻辑优化
- Pool的使用
### 渲染性能优化
- UI/场景优化
- 指定制作规范
### 内存优化
- 合理合图
- 资源压缩
- 资源分包
### 流量优化
- 减少网络总类
- 合并网络包

