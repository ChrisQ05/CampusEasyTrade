# CampusEasyTrade项目结构

```plaintext
CampusUsedGoodsSystem/
├── CampusUsedGoodsSystem.sln              # Visual Studio解决方案文件
├── CampusUsedGoodsSystem.vcxproj         # 项目文件
├── src/
│   ├── main.cpp                          # 项目主文件
│   │
│   ├── Core/                             
│   │   ├── definitions.h                 # 所有数据结构定义
│   │   ├── utils.h                       # 工具函数声明
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
│   │   │   └── user_manager.cpp          # 用户管理实现
│   │   │
│   │   ├── GoodsManager/                 
│   │   │   ├── goods_manager.h          # 商品管理接口
│   │   │   └── goods_manager.cpp         # 商品管理实现
│   │   │
│   │   ├── TransactionManager/           
│   │   │   ├── transaction_manager.h     # 交易管理接口
│   │   │   └── transaction_manager.cpp    # 交易管理实现
│   │   │
│   │   ├── Innovation/                   # 创新功能模块
│   │   │   ├── MapNavigation/           
│   │   │   │   ├── map_navigation.h     
│   │   │   │   └── map_navigation.cpp   
│   │   │   │
│   │   │   ├── LivePreview/              
│   │   │   │   ├── live_preview.h       
│   │   │   │   └── live_preview.cpp     
│   │   │   │
│   │   │   ├── AIEvaluation/             
│   │   │   │   ├── ai_evaluation.h      
│   │   │   │   └── ai_evaluation.cpp    
│   │   │   │
│   │   │   ├── CourseMaterial/           
│   │   │   │   ├── course_material.h    
│   │   │   │   └── course_material.cpp  
│   │   │   │
│   │   │   └── CampusActivities/          
│   │   │       ├── campus_activities.h  
│   │   │       └── campus_activities.cpp
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
