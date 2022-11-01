# unity1
## unity
#### 变量

==变量起名原则：变量名.动作.形式==
   1. eg. anim.GetBool(“变量名”)
   2. 大写表示函数，小写表示当前物体的变量

+ *public* 可用在函数之内也可用在函数之外
+ *private* 仅能用在当前函数之内
+ *Input.GetAxis*返回虚拟轴的值值固定在（-1，1）之间（平滑）
+ *Input.GetAxis* 返回虚拟轴的值固定在-1，0，1三个数之间
+ *Horizontal*水平轴线
   1. eg.如果想让动作目标向左或者向右动
   2. float 变量名=Input.GetAxis(“轴线“）；
   3. if(变量名！=0）【刚体速度（定义刚体名.速度velocity）=new Vector2D(变量名*变量，刚体.速度.y)】
+ *velocity* 变量名.velocity这个变量的速度变化
+ *vector* 层面中的移动变化里包含变量（如果为2D则中包含x,y；如果为3D则包含x,y,z）
+ *constrain*锁定方向
+ *time.deltatime* 调整物理运行时中的百分比使运行更平滑 例如加在「变量名*变量*time. deltatime }上（保证在各种CPU下都是同种速度）
+ *刚体变量* public Rigidbody rb此时rb为变量名称
+ *跳跃*  if(变量！=0）
+ *transform. locolScale =new Vector3(变量名，1，1）*
+ *Animator.SetFloat*将浮点值发送到动画器已影响过度 
+ *Collider2D.IsTouchingLayers（要检查的图层）* 检查该碰撞体是否正在接触指定layerMask上的任何碰撞体

####  变量类型

+ *int* 整形
+ *float* 浮点型(浮点型后要加f 例如 float a=5.5f)
+ *bool* 布尔型（当没有写=true 时默认为false
+ *数组* 可以写为int[] num= new int [3];
  数组长度为name.Length  
+ *game object* Game object中的一个对象 
+ *Input.get*
  1. 若要从键盘获取（Input.GetKeydown(KeyCode.D))
  2. 当按键按下的时候（Input.GetButtondown(“Jump”)//这个Jump是在项目设置里面系统自带的需要统一
  3. 当从键盘中获取1-0--1这些数时，（Input.GetAxis(“”);)
  4. 当从键盘中只获得-1 0 1这三个数时（Input.GetAxisRaw(“”);)

#### 函数 

==函数与函数之间也可以互相调用==

+ *Start* 每当游戏开始时按住按钮后执行Start里的语句
+ *Update* 每一帧会执行一次
+ *FixedUpdate* 调整帧数以便让各种配置运行
+ *Awake* 无论script是否启动，都在开始的时候执行
+ *Input* 输入变量值形式为（Input.Gets____（“变量名”）；）
+ *Switch+变量名* 变换动画
+ *OnCollisionEnter2D* 当碰撞效果发生时，执行2D操作
  1. 与OnTriggerEter2D的区别：Collision具有物理碰撞效果，Trigger没有碰撞效果

#### 类

+ *debug* 
  1. * Debug.Log* 输出字符串 
  2. * 字符串声明（string ｉ=“MYNAME”）可以直接写Debug.Log(“MYNAME”);也可以写成Debug.Log(i);
  3. Debug使用方法：
     1. Debug.Log(变量名1+“（输出变量1的值）需要输出内容（输出变量2的值）”+变量名2）
        1. 例如：int i=2; 
        2. int n=4;
        3. Debug.Log(i+”add 2 is”+n);
        4. 则输出2 add 2 is 4;
     2. 还可以用四则运算（+ - * /），在同级运算符的情况下将先运算的括起来
     3. 运用Debug log 输出时调用函数情况：
        1. 例如：在调用函数a(int name,int age,bool isBoy)中输出:
        2. Debug.Log(“Name:”+name+”Age:”+age+”,He is a boy!”)
        3. 则主函数中应这样调用：
        4. a(“mourn”,33,true);(其中可以用变量直接表示）
        5. 则输出形式：Name:mouren Age:33,He is a boy!
+ *Transform*一个类，用来描述物体的位置，大小，旋转等信息。
  1. transform.position 移动选中物体（x,y轴变化）
     1. 例如：transform.position=new Vector2(transform.position.x+1,0);其中的 transform.position.x代表x中位置的变量，整体是一个变量
+ *Game object* 创建变量的类==引擎自带== 所有初始变量都为Game object 后创建改名 
  1. 使用时调用该Game object （其中含有多个component固定有一个transform） 
+ *class* 调用函数的类，调用任何函数在后面都要加（ MonoBehaviour )
  1. 写法如：public class (名字)： MonoBehaviour ;==该声明位于头文件后中包含所有用到的函数（用花括号括起来==
     [脚本以及更多函数](https://docs.unity.cn/cn/2022.1/ScriptReference/index.html)
+ *Order of Execution for Event Functions*代码执行流程图

#### 图层

+ *排序图层* 改变图层时注意先后顺序（越在下面的越显示在前面，同样数字大的也显示在前面）
  地图创建
+ 添加最小元素 

#### 页面中元素

+ *项目目录* -Assets
+ *Pixels Per Unit* 像素格
+ *Tilemap* 瓦片地图 在空白位置中添加
+ *Tile .Palette*  Window-2D 并创建新文件夹
+ *Sprite* 一个精灵可以承载项目里的各种内容
      如果要将素材切割，现将Mode中的元素从单一改为多元，再将Editor中slice切割（自己定义-crid by cell size) aply 确定
+ *项目设置*中可以查看跳跃等键盘按键可以自定义修改（Input Axis)
+ *Horizontal* 横向

#### 组件 component （组件）是在游戏中某些功能的集合

+ *Rigidbody 2D* 刚体包含重力等
+ *Box Collider 2D* 给人物角色添加矩形物理碰撞体（如果人物只能左右移动不能旋转应冻结z轴防止人物角色乱串
+ *tilemap Rigidbody 2D* 瓦片地图刚体
+ *Script* 脚本点击添加New Script后在Assets中创建c#脚本拖入文件夹中拽到相应对象里，在VS中编辑可添加变量
+ *Script Renderer 渲染
+ *scale*缩放比例
+ *Animator* Window-Animator-Animator (动画-动画）显示时间轴将动作添加进去
+ *Animator parameter* 添加类型
+ *Animation* 动画器，显示联系及参数
+ *Animator* 添加动画（用文件夹来存放动画在文件夹里放Animator Controler）
  Window-Animation-Animation
  Animator 检查器中参数的Condition可添加速度Greater 大于；Less小于；
+ *Loop time* 循环播放
+ *make translation *制造联系
+ *添加参数* Animator-parameter
+ *translation Duration* 转换
+ *Composite Collider 2D*将部分化为整体（前提是有刚体）(以防出现卡脚）
  1. *Cinemachine Confiner* 帮助找到镜头位置
+ *Polygon Collider 2D*多边形碰撞体固定到背景图页面
  1. *OnDrawGiznos* 地面检测 中写 Giznos.DrawWireSphere(GroundCheck.position,半径大小f); 

#### 创建游戏角色的方法

1. 直接在文件夹中找到player拖拽
2. 或者在目录里新建项目（sprite)将游戏角色拖拽到Sprite里面

#### 操作

1. 游戏中的任何操作都要在C#文件里声明，如添加变量控制组件 
2. 简化变量，代码将public型的变量改为Private型
   1. 在下面写：变量名=GetComponent.<变量类型>()
3. 将private型变量在主页面中显示，在声明变量时private前面加上[SerializeField]
4. 镜头控制
   1. 在主摄影机上添加脚本，脚本中添加位置移动函数，使镜头（在每一帧）跟着目标对象（控制对象）走
   2. 用Cinemachine创建2D摄像头，控制相关对象（将z轴改成负值即可看到窗口调摄像区域页面）
   3. 跟踪游戏角色
5. 添加背景图至全部
   1. 现将背景复制多个后拖动原背景x轴将页面覆盖满
   2. 再添加Confiner，在背景中添加多变形碰撞体将页面固定在有背景图范围之内（如果人物掉下去把是触发器勾选上）
6. 防止出现跳跃卡顿粘连情况，添加物理材质改变摩擦力，或改变2D刚体的碰撞检测和休眠模式）
7. 碰撞体开关-是触发器
8. 将目录里已经创建好的物体拖入新文件夹中——预制（可在下一次创建的时候直接调用）
9. 聚焦——control+F
10. 添加UI视图——添加图布——添加文档——设置视图
11. 整形变成字符型——ToString()
12. 将UI视图中的项目锁定（可用于各种大小比例屏幕）改变Rect transform 里的错点预设即可完成
13. 如果要拖拽物体，将游戏角色设为项目的字目录（在代码中实现，判断当游戏角色触发什么条件时将该游戏角色赋给他的子目录）
14. 让物体位于两者之间横跳，再物体下创建子目录，设置两个变量将文件夹拖入，转换移动方向，transform.localScale=new Vector(1,2,3);，解开父子目录联系 DetachChildren（）；
     第二个方法——使变量获得初始位置的值，然后改变值

> public ....
> Start{
> Destroy(leftpoint.gameObject);
> Destroy(rightpoint.gameObject);
> }
> if( Faceleft ){ 
> bring.velocity=new Vector2(-Speed,rb.velocity.y);
> if(transform.positions< leftpoint.position.x){
> transform.localScale=new Vector3(-1,1,1);
> Faceleft =false;
> } 
> }
> else{...} 

15. 若设置角色自动
  16. 先进行某动作后进行某动作时可以在动画中添加（竖条）event保证动画在某个动作前或某个动作后进行。
  17. 添加event时应该在该event的功能中添加动作效果
18. 调用函数：调用的函数名 局部变量（调用函数给函数附的一个变量）=函数里的变量.gameObject.GetComponent<调用的函数名>();

> 
