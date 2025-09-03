```mermaid
flowchart LR
    %% 层次分组用不同背景颜色
    subgraph UI["UI 用户界面层"]
        style UI fill:#e7f5ff,stroke:#1c7ed6,stroke-width:2px
        ui1["🟦 主菜单"]
        ui2["🟦 登录注册"]
        ui3["🟦 物品管理"]
        ui4["🟦 信用评价"]
        ui5["🟦 搜索界面"]
        ui6["🟦 发布物品"]
        ui7["🟦 交易历史"]
        ui8["🟦 管理后台"]
        uimgr["👩‍💻 UI管理器"]
    end

    subgraph BL["BL 业务逻辑层"]
        style BL fill:#fff9db,stroke:#f59f00,stroke-width:2px
        itemMgr["📦 物品管理器"]
        userMgr["👤 用户管理器"]
        creditSys["🌟 信用系统"]
    end

    subgraph DL["DL 数据管理层"]
        style DL fill:#e6fcf5,stroke:#12b886,stroke-width:2px
        dataMgr["📚 数据管理器"]
        userDataMgr["📋 用户数据管理器"]
        creditDataMgr["🌟 信用数据管理器"]
    end

    subgraph SL["SL 数据存储层"]
        style SL fill:#fff0f6,stroke:#ae3ec9,stroke-width:2px
        items[["📄 items.txt"]]
        users[["📄 users.txt"]]
        tx[["📄 transactions.txt"]]
        reviews[["📄 reviews.txt"]]
        credit[["📄 credit_profiles.txt"]]
    end

    subgraph ML["ML 模型层"]
        style ML fill:#f8f9fa,stroke:#212529,stroke-width:2px
        itemStruct[["📦 Item"]]
        userStruct[["👤 User"]]
        txStruct[["🔄 Transaction"]]
        reviewStruct[["🔍 Review"]]
        creditStruct[["🌟 UserCreditProfile"]]
    end

    %% 连接关系
    ui2 --> userMgr
    ui3 --> itemMgr
    ui4 --> creditSys
    ui5 --> itemMgr
    ui6 --> itemMgr
    ui7 --> creditSys
    ui8 --> userMgr

    itemMgr --> dataMgr
    userMgr --> userDataMgr
    creditSys --> creditDataMgr

    dataMgr --> items
    dataMgr --> tx
    userDataMgr --> users
    creditDataMgr --> reviews
    creditDataMgr --> credit

    items -.-> itemStruct
    users -.-> userStruct
    tx -.-> txStruct
    reviews -.-> reviewStruct
    credit -.-> creditStruct
