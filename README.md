# deepThought
一个聊天机器人

>  The answer to life, universe and everything is 42   --deepThought

# 目标
*  具有从真实对话或语料库中学习的能力
 *  有泛化能力
*  能从自然语言中推测用户意图
*  针对意图，给予恰当回答（回调任务模块）
*  构造通用的解析工具，将自然语言解析为结构化信息

# 核心概念
*  意图 (intent)
*  实体 (Entity)
*  结构化的输出
  *  实体的模式 
*  require请求补齐
*  上下文环境 (context)
 *  session


# 设计
*  插件化
  *  输入/输出
  *  存储
  *  逻辑单元
*  事件驱动（意图）
*  让数据在管道中流动
*  区分两类bot
 *  闲聊型
   *  学习人类说话
     *  在对话中学习 
 *  助理型
   *  领域知识
   *  搜索
*  rich output
 *  不要放弃超链（支持富文本输出）
  * 采用ipython交互做实验
   *  `from IPython.display import HTML, Image, YouTubeVideo`

# 涉及知识
*  自然语言处理（NLP）
  *  中文分词
  *  命名实体识别
*  模式匹配(Haskell)
 *  借鉴lisp
*  机器学习
  *  朴素贝叶斯
*  RNN
 *  LSTM

# 思路
### 提取结构化信息
*  通过命名实体识别等取出语言的结构，之后转化为其他问题：
 *  作为机器学习的特征向量
 *  模式匹配问题（lisp）
*  结构化的信息可以作为函数的变量，以此来对接业务系统（database/RESTful）

### intent的促发条件
*  intent的促发可以有依赖条件（类比django中的@require）,由此进一步向用户索求信息，以不足促发条件

# 语料库
*  电影字幕
*  小说台词
  * 古龙
*  构建openbot，开发技术和接口，也开放语料库，大家一起来收集真实语料库，通过开源和协议说明来处理隐私问题


# Todo
*  将wit作为bot的一个logic adapter
 *  添加timeout 

# Done
*  bot作为一个RESTful服务
*  对接微信，作为自动回复机器人
*  运行在树莓派上（长期稳定）
*  文字 -> 语音
