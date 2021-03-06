# 家政服务 原生微信小程序

## 微信小程序 开通
### 注册认证——==微信收300元审核费用==
https://jingyan.baidu.com/article/a948d6511bd5cb0a2dcd2e8f.html
+ 资料提供
    - 邮箱（没有注册过微信相关业务的邮箱）
    - 企业营业执照扫描件（或照片）或个体工商户执照
    - 能收款的企业对公账户（或个体工商户对应的银行卡）
    - 指派一位管理员（可以是法人或者委托的任何人）。需要管理员的个人微信号，且必须绑定和管理员身份证相符的银行卡。
    - 管理员身份证扫描件（或照片）
    - 座机号
    - 企业公章（个体工商户不需要）
    - 其他证书，如食品卫生许可证等（根据经营范围不同，证件不同）

### 申请微信支付
+ 总体流程：https://zhidao.baidu.com/question/2057900240876659187.html
  - 申请微信支付。小程序认证以后，可以在小程序后台，微信支付菜单栏，申请微信支付。填写企业信息和对公账户，微信支付会打一笔随机金额到对公账户，输入金额完成验证后，在线签署迁移，即完成了微信支付的申请流程。
  - 微信支付申请完，会发送微信支付商户号，商户平台用户名密码等信息到注册者邮箱。
+ 申请的具体流程：https://jingyan.baidu.com/article/4f34706e2f9744e387b56d27.html
+ 企业的微信小程序已认证后可在后台申请微信支付

------------------------------------
## 小程序开发功能点
### 功能点
+ 共10个页面，还有2个页面待确认
    - 服务下单
    - 分类列表
    - 预约详情
    - 预约
    - 我的预约
    - 退款
    - 客服评价
    - 评论
    - 会员中心
    - 资料编辑
    - 评论列表（待确认）
    - 评论详情（待确认）

### 前端开发
+ 开发时间评估
    - 前端页面输出：3日/人
    - 与后端接口联调：3日/人（读写接口） + 2日/人（微信支付/退款）
    
### 前端调用后端提供的接口
目测页面读写接口共11个，还有3个待确认。
其他需打通的接口：微信支付/退款等

+ 服务下单（1个）
  - 广告轮播图（是否可点击跳转页面？———— 目前不需要）
  - 服务大类列表
    - 服务大类id
    - 服务大类名称
    - 服务大类icon

+ 分类列表（1个）
  + 服务大类对应的服务项列表
    - 服务项id
    - 服务项名称
    - 服务项图片
    - 预约定金

+ 服务项预约详情（1个）
  + 服务项详情
    - 服务项id
    - 服务项名称
    - 介绍详情
    - 预约定金

+ 预约（可批量预约下单多个服务项）（1个）
  + ==微信支付————后端打通，流程查阅[http://www.jianshu.com/p/72f5c1e3f8a5]==
  + 表单提交
    - 预约用户信息：姓名、电话、预约时间、地址、备注
    - 服务项id列表
    - 服务项对应下单数量（定金总和）

+ 我的预约（订单管理）（2个）
  + 我的预约列表
    - 预约订单id
    - 预约项id列表
    - 预约项名称列表
    - 预约定金总和
    - 预约时间
    - 预约状况：是否已支付、是否已消费
  + 删除预约订单
  + 支付（未支付的订单）
  + 退款（已支付的订单）

+ 退款（1个）
  + ==退款提交==
    - 预约订单id
    - 退款说明

+ 客服评价（1个）
  - 公告
  - 地图定位（后端提供经纬度，还是商家地址固定前端来写死？）
  - 客服电话
  - 商家介绍
  - 商家点评总分
  - 全部评论展示

+ 评论（1个）
  + 评论提交
    - 评分
    - 评论留言
    - 图片（限制多少张数量）

+ 会员中心-编辑资料（2个）
  + 用户资料读取
    - 姓名（最开始读取用户登录的微信号昵称）————进入小程序的时候，前端就读取到用户的微信号昵称，提交给后端进行保存
    - 性别
    - 手机号
    - 地址
    - 自我介绍
  + 用户资料编辑提交（可进行单项提交保存）
    - 姓名
    - 性别
    - 手机号
    - 地址
    - 自我介绍

+ ==口碑管理（查看我的评论列表，评论展示，评论删除）（3个）————是否实现此功能？==


