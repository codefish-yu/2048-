游戏2048
1. 架构
* bll.py 业务business 逻辑logic 层layer
 负责处理程序的业务逻辑
 
* usl.py 用户user 显示show 层Layer 负责处理界面逻辑
* model.py 数据模型　负责描述项目中需要操作的数据
* main.py 入口模块/程序主模块，要保证这里面的代码越少越好
2. 执行流程
* main --> usl -->bll(model数据层被usl和bll共用)
3. 步骤
* 将核心算法(函数)移动到bll.py的GameCoreController(实例方法)
* 生成新数字
   * 需求
      * 2(90%) 4(10%)
      * 在随机(为零)位置上
   * 思路
      * 记录所有空白位置(行索引/列索引)
      * 随机选择一个空白位置,存入新数字
      * 判断游戏是否结束
         * 如果存在空白位置，游戏不结束
         * 如果水平方向,存在相同元素则游戏不结束
         * 如果垂直方向,存在相同元素则游戏不结束
         * 以上条件都不满足,游戏结束