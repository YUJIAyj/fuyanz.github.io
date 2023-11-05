---
coverY: 0
---

# 🐸 Unity3D脚本编程与游戏开发

## 1.1 控制物体的运动

### 1.1.2 Start和Update事件

Start()函数在游戏开始运行的时候执行一次，特别适合进行组件初始化。

Update()函数每帧都会执行，在不同设备上更新的频率有所区别。

Start()在组件开始运行调用。

Update()更新该组件调用。

Debug.Log()用于向控制台输出信息。

```csharp
Debug.Log("组件开始执行");
```

### 1.1.3 修改物体位置

实际上就是修改Transform组件的数据。

#### 两种方法

* 使用Translate()函数

```csharp
transform.Translate(1.5f,0,0);//沿着自身右侧方向前进1.5个单位
```

* 直接指定新的位置

```csharp
transform.position=new Vector3(1,4,6);
```

#### 连续位移动画

让物体每帧都移动很小的距离。

把改变位置的代码写在Update()函数里。

```csharp
void Update(){
    transform.Translate(0,0,0.3f);
    //or
    transform.position+=new Vector3(0,0,0.3f);
```

#### 保证不同主机运行距离都相同

```
void Update(){
    transform.Translate(0,0,0.3f*Time.deltaTime);
    //or
    transform.position+=new Vector3(0,0,0.3f*Time.deltaTime);
```
