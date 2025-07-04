# CampusEasyTrade项目结构

```plaintext
CampusUsedGoodsSystem/
├── CampusUsedGoodsSystem.sln              # Visual Studio解决方案文件
├── CampusUsedGoodsSystem.vcxproj         # 项目文件
├── src/
│   ├── main.cpp                          # 项目主文件，负责初始化和主循环
│   │
│   ├── Core/                             # 核心数据结构和全局定义存
│   │   ├── definitions.h                 # 存放所有 typedef struct (User, Goods, Transaction, MapLocation等)
│   │   ├── utils.h                       # 通用工具函数，如ID生成、时间转换、字符串处理等
│   │   └── utils.cpp                     # 工具函数实现
│   │
│   ├── DataAccess/                       
│   │   ├── data_access.h                 # 数据访问接口
│   │   ├── data_access.cpp               # 数据访问实现
│   │   └── data_models.h                 # 复杂数据模型定义
│   │
│   ├── Application/                      
│   │   ├── UserManager/                  
│   │   │   ├── user_manager.h           # 用户管理接口
│   │   │   └── user_manager.cpp          # 用户注册、登录、信息管理、信用分
│   │   │
│   │   ├── GoodsManager/                 
│   │   │   ├── goods_manager.h          # 商品管理接口
│   │   │   └── goods_manager.cpp         # 商品发布、浏览、搜索、状态管理、收藏
│   │   │
│   │   ├── TransactionManager/           
│   │   │   ├── transaction_manager.h     # 交易管理接口
│   │   │   └── transaction_manager.cpp    # 购物车、订单、交易、评价
│   │   │
│   │   ├── Innovation/                   # 创新功能模块
│   │   │   ├── MapNavigation/           
│   │   │   │   ├── map_navigation.h     
│   │   │   │   └── map_navigation.cpp   # 地图绘制、路径规划、取货点
│   │   │   │
│   │   │   ├── AIEvaluation/             
│   │   │   │   ├── ai_evaluation.h      
│   │   │   │   └── ai_evaluation.cpp    # 智能估价算法、图表生成
│   │   │   │
│   │   │   ├── CourseMaterial/           
│   │   │   │   ├── course_material.h    
│   │   │   │   └── course_material.cpp  # 课程资料管理、审核
│   │   │   │   
│   │   │   │
│   │   │   └── CampusActivities/          
│   │   │       ├── campus_activities.h  
│   │   │       └── campus_activities.cpp # 活动融合、主题市集
│   │   │
│   │   └── SystemUtils/                  # 辅助功能模块
│   │       ├── security_system.h         
│   │       ├── security_system.cpp       
│   │       ├── notification_system.h     
│   │       ├── notification_system.cpp  
│   │       ├── data_analysis.h           
│   │       └── data_analysis.cpp        
│   │
│   └── UI/                               # 用户界面层
│       ├── ui_manager.h                  # UI管理接口
│       ├── ui_manager.cpp                # UI管理实现
│       │
│       ├── pages/                        # 各页面实现
│       │   ├── login_page.h              
│       │   ├── login_page.cpp            
│       │   ├── main_menu_page.h          
│       │   ├── main_menu_page.cpp        
│       │   ├── goods_list_page.h         
│       │   ├── goods_list_page.cpp       
│       │   ├── goods_detail_page.h       
│       │   ├── goods_detail_page.cpp     
│       │   ├── user_profile_page.h       
│       │   ├── user_profile_page.cpp     
│       │   ├── publish_page.h            
│       │   ├── publish_page.cpp          
│       │   ├── map_page.h                
│       │   └── map_page.cpp              
│       │
│       └── easyx_wrapper.h               # EasyX封装工具
├── data/                                 # 运行时数据文件
│   ├── users.dat                         
│   ├── goods.dat                         
│   ├── transactions.dat                  
│   ├── map_locations.dat                
│   └── sensitive_words.txt              
│
├── assets/                               # 静态资源
│   ├── backgrounds/                      
│   │   ├── login_bg.jpg                 
│   │   └── main_bg.jpg                  
│   │
│   ├── icons/                           
│   │   ├── book_icon.png                
│   │   ├── electronics_icon.png         
│   │   └── clothing_icon.png            
│   │
│   ├── campus_map.png                   # 校园地图
│   └── logo.png                         # 系统logo
│
├── docs/                                 # 项目文档
│   ├── README.md                        
│   ├── design_document.md               
│   └── api_reference.md                 
│
└── build/                               # 编译输出目录 (Visual Studio自动管理)
