#### 文章目录 

 *   *   *  [🧡 Unity知识面试篇][Unity]
         *  [基础流程][Link 1]
         *   *  [1.3d内容生产和编辑流程][1.3d]
             *  [2. Unity工作流程][2. Unity]
             *  [3.unity生命周期][3.unity]
         *  [物理系统][Link 2]
         *   *  [1.CharacterController 与 Rigidbody 的区别][1.CharacterController _ Rigidbody]
             *  [2.射线检测碰撞物的原理][2.]
             *  [3.链条关节 (Hinge Joint) 的概念和用途][3._ _Hinge Joint_]
             *  [4.物体发生碰撞的必要条件][4.]
             *  [5.碰撞过程的不同阶段及其对应的函数][5.]
             *  [6.Unity3D 中碰撞器和触发器的区别][6.Unity3D]
             *  [7.射线 Raycast 原理][7._ Raycast]
             *  [8.Unity3D 物理引擎中施加力的方式][8.Unity3D]
             *  [9.高速物体与大物体碰撞可能出现的问题及解决方法][9.]
             *  [10.物理更新适用的系统函数 FixedUpdate][10._ FixedUpdate]
             *  [11. Unity中构建复杂场景的经验][11. Unity]
         *  [UI & 2D 部分][UI _ 2D]
         *   *  [1.UGUI 合批问题][1.UGUI]
             *  [2.Image 与 RawImage 的区别][2.Image _ RawImage]
             *  [3.实现 2D 游戏的不同方式][3._ 2D]
             *  [4.TextureType 选项为 Texture 和 Sprite 的区别][4.TextureType _ Texture _ Sprite]
             *  [5.保持 UI 在不同分辨率下一致性的方法][5._ UI]
             *  [6.画布的三种模式和缩放模式][6.]
             *  [7.Text 与 TMPText 的区别及优缺点][7.Text _ TMPText]
         *  [动画系统][Link 3]
         *   *  [1.游戏动画的种类及其原理][1.]
             *  [2.Avatar 的作用][2.Avatar]
             *  [3.反向旋转动画的方法][3.]
             *  [4.Animation.CrossFade 的用途][4.Animation.CrossFade]
             *  [5.Animation 的五个方法][5.Animation]
             *  [6.SkinnedMesh 实现原理][6.SkinnedMesh]
             *  [7.动画层 (Animation Layers) 的作用][7._ _Animation Layers_]
             *  [8.Animation 与 Animator 的区别][8.Animation _ Animator]
             *  [4. 导入和操作3D模型以及使用Unity动画系统][4. _3D_Unity]
         *  [协程][Link 4]
         *   *  [1.进程、线程、协程的概念][1. 1]
             *  [2.协程的作用和底层原理][2. 1]
             *  [3.线程与协程的区别][3. 1]
             *  [4.协同程序的执行代码、用处和缺点][4. 1]
         *  [数据持久化 & 资源管理&性能优化][Link 5]
         *   *  [1.Unity 常用资源路径][1.Unity]
             *  [2.安全地在不同工程间迁移 asset 数据的方法][2._ asset]
             *  [3.PlayerPrefs 类保存和读取整形数据的函数][3.PlayerPrefs]
             *  [4.动态加载资源的方式][4. 2]
             *  [5.AssetsBundle 打包和加载方法][5.AssetsBundle]
             *  [6.AssetBundle 卸载流程][6.AssetBundle]
             *  [7.ScriptableObject 的用途和优势][7.ScriptableObject]
             *  [8.热更新][8.]
         *  [C\#][C]
         *   *  [1.什么是反射以及反射的原理][1. 2]

#### 🧡 Unity知识面试篇 

#### 基础流程 

##### 1.3d内容生产和编辑流程 

3D内容生产和编辑流程通常包括一系列复杂的步骤，从最初的概念设计到最终的渲染和输出。以下是3D内容生产和编辑的一般流程：

1.  概念设计：
    
     *  确定3D内容的基本构思，包括角色、环境、对象等的视觉风格和功能需求。
2.  创建3D模型：
    
     *  使用3D建模软件（如Blender、Maya、3ds Max）创建基础的几何形状和详细模型。
3.  拓扑优化：
    
     *  优化3D模型的拓扑结构，确保模型在保持细节的同时具有高效的多边形分布。
4.  UV展开：
    
     *  将3D模型的表面展开成2D平面，为纹理贴图做准备。
5.  纹理贴图：
    
     *  创建和应用纹理贴图，包括漫反射贴图、法线贴图、高光贴图等，以增加模型的真实感。
6.  材质和着色：
    
     *  设计材质和着色器，定义物体表面的视觉特性，如颜色、光泽、透明度等。
7.  骨骼绑定和蒙皮：
    
     *  对于角色或可动物体，创建骨骼系统并绑定到模型上，以便进行动画制作。
8.  动画制作：
    
     *  使用关键帧动画或运动捕捉技术制作角色或物体的动作和表情。
9.  环境布局：
    
     *  在3D场景中布置环境元素，如建筑物、自然景观、道具等。
10. 光照和阴影：
    
     *  设置场景的光照效果，包括光源类型、强度、颜色和阴影。
11. 摄像机设置：
    
     *  确定摄像机的位置和视角，设置镜头参数如焦距、景深等。
12. 渲染设置：
    
     *  配置渲染参数，包括分辨率、抗锯齿、采样率等，以获得高质量的图像输出。
13. 模拟和特效：
    
     *  添加物理模拟（如流体、布料、粒子效果）和特效（如光晕、烟雾）。
14. 后期处理：
    
     *  使用后期处理技术，如颜色校正、滤镜效果、合成等，增强视觉效果。
15. 性能优化：
    
     *  优化3D场景和动画的性能，确保在目标平台上的流畅运行。
16. 最终渲染：
    
     *  进行最终渲染，输出高分辨率的图像或动画序列。
17. 视频编辑和输出：
    
     *  如果是动画或视频项目，进行视频编辑和后期剪辑，然后输出最终视频文件。
18. 反馈和迭代：
    
     *  根据反馈进行必要的调整和优化，迭代改进3D内容。
19. 发布和分发：
    
     *  将完成的3D内容发布到相应的平台或媒体，进行市场推广和分发。

##### 2. Unity工作流程 

 *  项目设置：创建新的Unity项目，设置项目的基本参数，如质量设置和物理引擎。
 *  资产导入：将3D模型、纹理、音频文件等资源导入Unity。
 *  场景构建：在Unity编辑器中布局场景，包括地形、建筑物、道具等。
 *  游戏对象创建：创建游戏对象（GameObject），并附加组件如Collider、Rigidbody等。
 *  脚本编写：使用C\#或其他支持的语言编写脚本，实现游戏逻辑。
 *  动画制作：使用Unity动画系统创建角色和物体的动画。
 *  UI设计：设计和实现用户界面，包括菜单、HUD、控制面板等。
 *  测试：在编辑器中进行游戏测试，使用Unity的测试工具进行自动化测试。
 *  性能优化：使用Profiler工具分析和优化游戏性能。
 *  构建和发布：配置构建设置，将游戏构建为可执行文件，并发布到目标平台。

##### 3.unity生命周期 

Unity中的生命周期指的是游戏对象（GameObject）和组件从创建到销毁所经历的一系列系统调用过程。理解Unity的生命周期对于管理游戏状态、执行初始化和清理操作非常重要。以下是Unity中的主要生命周期阶段：

1.  Awake：
    
     *  在对象首次成为激活状态时调用，用于初始化。在任何Start方法之前调用，且只会调用一次。
2.  OnEnable：
    
     *  当对象被激活时调用，可以被调用多次，例如当对象从非激活变为激活状态时。
3.  Start：
    
     *  在脚本第一次加载到游戏对象上时调用，通常用于初始化操作，如设置变量和启动Coroutine。
4.  Update：
    
     *  每帧调用一次，主要用于处理游戏逻辑、玩家输入和时间相关的更新。
5.  FixedUpdate：
    
     *  在物理计算之前每固定时间间隔调用一次，主要用于物理相关的更新。
6.  LateUpdate：
    
     *  在Update之后调用，用于执行应该在所有Update方法之后发生的操作。
7.  OnLevelLoad：
    
     *  当加载新场景时调用，可以用于设置场景特定的状态。
8.  OnDisable：
    
     *  当对象变为非激活状态时调用，可以用于保存状态或执行清理操作。
9.  \*\* OnDestroy\*\*：
    
     *  当对象被销毁时调用，用于执行必要的清理工作，如取消Coroutine、移除事件监听等。
10. OnDrawGizmos / OnDrawGizmosSelected：
    
     *  用于在场景视图和游戏视图中绘制辅助的Gizmos，帮助开发者可视化组件的位置和方向。
11. OnGUI：
    
     *  虽然在较新的Unity版本中已不推荐使用，但在过去用于在Unity编辑器中绘制自定义的图形用户界面。
12. OnApplicationPause：
    
     *  当应用程序暂停时调用，例如移动设备被切换到后台。
13. OnApplicationQuit：
    
     *  当应用程序退出时调用，用于执行最后的清理工作。
14. OnCollisionEnter / OnCollisionStay / OnCollisionExit


[Unity]: #_Unity_2
[Link 1]: #_4
[1.3d]: #13d_5
[2. Unity]: #2_Unity_66
[3.unity]: #3unity_79
[Link 2]: #_137
[1.CharacterController _ Rigidbody]: #1CharacterController__Rigidbody__139
[2.]: #2_143
[3._ _Hinge Joint_]: #3_Hinge_Joint__146
[4.]: #4_149
[5.]: #5_152
[6.Unity3D]: #6Unity3D__157
[7._ Raycast]: #7_Raycast__160
[8.Unity3D]: #8Unity3D__163
[9.]: #9_169
[10._ FixedUpdate]: #10_FixedUpdate_173
[11. Unity]: #11_Unity_177
[UI _ 2D]: #UI__2D__183
[1.UGUI]: #1UGUI__185
[2.Image _ RawImage]: #2Image__RawImage__188
[3._ 2D]: #3_2D__195
[4.TextureType _ Texture _ Sprite]: #4TextureType__Texture__Sprite__201
[5._ UI]: #5_UI__205
[6.]: #6_211
[7.Text _ TMPText]: #7Text__TMPText__221
[Link 3]: #_233
[1.]: #1_235
[2.Avatar]: #2Avatar__240
[3.]: #3_243
[4.Animation.CrossFade]: #4AnimationCrossFade__246
[5.Animation]: #5Animation__249
[6.SkinnedMesh]: #6SkinnedMesh__256
[7._ _Animation Layers_]: #7_Animation_Layers__259
[8.Animation _ Animator]: #8Animation__Animator__262
[4. _3D_Unity]: #4_3DUnity_266
[Link 4]: #_273
[1. 1]: #1_275
[2. 1]: #2_280
[3. 1]: #3_284
[4. 1]: #4_288
[Link 5]: #___310
[1.Unity]: #1Unity__312
[2._ asset]: #2_asset__317
[3.PlayerPrefs]: #3PlayerPrefs__322
[4. 2]: #4_326
[5.AssetsBundle]: #5AssetsBundle__332
[6.AssetBundle]: #6AssetBundle__339
[7.ScriptableObject]: #7ScriptableObject__342
[8.]: #8_351
[C]: #C_386
[1. 2]: #1_387