```mermaid
flowchart TB
    %% ================== 用户界面层 ==================
    subgraph UI["用户界面层 (UI Layer)"]
        direction TB
        ui1["主菜单\nMain Menu"]
        ui2["登录注册\nLogin / Register"]
        ui3["物品管理\nItem Mgmt"]
        ui4["信用评价\nCredit Sys"]
        ui5["搜索界面\nSearch UI"]
        ui6["发布物品\nAdd Item"]
        ui7["交易历史\nTransaction History"]
        ui8["管理后台\nAdmin Panel"]
        uimgr["UI Manager\n(ui_manager.cpp/.h)"]
    end

    %% ================== 业务逻辑层 ==================
    subgraph BL["业务逻辑层 (Business Layer)"]
        direction TB
        itemMgr["Item Manager\n(item_manager.cpp/.h)"]
        userMgr["User Manager\n(user_manager.cpp/.h)"]
        creditSys["Credit System\n(credit_system.cpp/.h)"]
    end

    %% ================== 数据管理层 ==================
    subgraph DL["数据管理层 (Data Layer)"]
        direction TB
        dataMgr["Data Manager\n(data_manager.cpp/.h)"]
        userDataMgr["User Data Manager\n(user_data_manager.cpp/.h)"]
        creditDataMgr["Credit Data Manager\n(credit_system.cpp)"]
    end

    %% ================== 数据存储层 ==================
    subgraph SL["数据存储层 (Storage Layer)"]
        direction TB
        items[["items.txt\n物品数据 CSV"]]
        users[["users.txt\n用户数据 CSV"]]
        tx[["transactions.txt\n交易记录 CSV"]]
        reviews[["reviews.txt\n评价数据 CSV"]]
        credit[["credit_profiles.txt\n信誉档案 CSV"]]
    end

    %% ================== 模型层 ==================
    subgraph ML["模型层 (Model Layer)"]
        direction LR
        itemStruct[["Item\n物品结构"]]
        userStruct[["User\n用户结构"]]
        txStruct[["Transaction\n交易结构"]]
        reviewStruct[["Review\n评价结构"]]
        creditStruct[["UserCreditProfile\n信誉档案结构"]]
    end

    %% ================== 调用关系 ==================
    %% UI -> Business
    ui2 --> userMgr
    ui3 --> itemMgr
    ui4 --> creditSys
    ui5 --> itemMgr
    ui6 --> itemMgr
    ui7 --> creditSys
    ui8 --> userMgr

    %% Business -> Data Layer
    itemMgr --> dataMgr
    userMgr --> userDataMgr
    creditSys --> creditDataMgr

    %% Data Layer -> Storage Layer
    dataMgr --> items
    dataMgr --> tx
    userDataMgr --> users
    creditDataMgr --> reviews
    creditDataMgr --> credit

    %% Model Layer 绑定
    items -.-> itemStruct
    users -.-> userStruct
    tx -.-> txStruct
    reviews -.-> reviewStruct
    credit -.-> creditStruct

