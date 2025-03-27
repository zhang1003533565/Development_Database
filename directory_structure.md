# 环境与人类发展大数据分析平台目录结构

```
Development/                            # 项目根目录
├── manage.py                          # Django项目管理文件
├── README.md                          # 项目说明文档
├── requirements.txt                   # 项目依赖
├── .env                              # 环境变量配置
├── .gitignore                        # Git忽略文件
│
├── core/                             # Django核心配置目录
│   ├── __init__.py
│   ├── settings/                     # 配置文件目录
│   │   ├── __init__.py
│   │   ├── base.py                  # 基础配置
│   │   ├── development.py           # 开发环境配置
│   │   └── production.py            # 生产环境配置
│   ├── urls.py                      # 主URL配置
│   ├── asgi.py                      # ASGI配置
│   └── wsgi.py                      # WSGI配置
│
├── apps/                            # 应用目录
│   ├── meteorology/                 # 气象模块
│   │   ├── __init__.py
│   │   ├── models.py               # 数据模型
│   │   ├── views.py                # 视图函数
│   │   ├── urls.py                 # URL配置
│   │   ├── admin.py               # 管理界面配置
│   │   ├── apps.py                # 应用配置
│   │   ├── api/                   # API接口
│   │   │   ├── __init__.py
│   │   │   ├── serializers.py
│   │   │   └── views.py
│   │   └── services/              # 业务逻辑
│   │       ├── __init__.py
│   │       └── data_analysis.py
│   │
│   ├── environment/                # 环境模块
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── api/
│   │   └── services/
│   │
│   ├── resources/                  # 资源模块
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── api/
│   │   └── services/
│   │
│   ├── agriculture/                # 农业模块
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── api/
│   │   └── services/
│   │
│   ├── population/                 # 人口模块
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── api/
│   │   └── services/
│   │
│   ├── dashboard/                  # 仪表盘模块
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── api/
│   │   └── services/
│   │       ├── data_integration.py # 数据整合服务
│   │       └── visualization.py    # 可视化服务
│   │
│   └── ai_service/                 # AI服务模块
│       ├── __init__.py
│       ├── models.py
│       ├── views.py
│       ├── urls.py
│       ├── admin.py
│       ├── apps.py
│       ├── api/
│       └── services/
│           ├── deepseek_service.py
│           └── openai_service.py
│
├── static/                         # 静态文件目录
│   ├── css/
│   ├── js/
│   │   ├── charts/                # 图表组件
│   │   └── dashboard/             # 仪表盘组件
│   ├── images/
│   └── libs/                      # 第三方库
│
├── templates/                      # 模板目录
│   ├── base.html                  # 基础模板
│   ├── meteorology/
│   ├── environment/
│   ├── resources/
│   ├── agriculture/
│   ├── population/
│   ├── dashboard/
│   └── ai_service/
│
├── utils/                         # 工具函数目录
│   ├── __init__.py
│   ├── data_processors/
│   │   ├── meteorology/
│   │   ├── environment/
│   │   ├── resources/
│   │   ├── agriculture/
│   │   └── population/
│   ├── ai_utils/
│   └── common/
│
├── tests/                         # 测试目录
│   ├── __init__.py
│   ├── test_meteorology/
│   ├── test_environment/
│   ├── test_resources/
│   ├── test_agriculture/
│   ├── test_population/
│   ├── test_dashboard/
│   └── test_ai_service/
│
├── docs/                          # 文档目录
│   ├── api/
│   ├── deployment/
│   └── database/
│
├── scripts/                       # 脚本目录
│   ├── data_import/
│   │   ├── meteorology/
│   │   ├── environment/
│   │   ├── resources/
│   │   ├── agriculture/
│   │   └── population/
│   ├── data_export/
│   └── deployment/
│
└── logs/                          # 日志目录
    ├── error.log
    ├── info.log
    └── debug.log
```

## 目录说明

### 1. 核心文件
- **manage.py**: Django项目管理脚本
- **core/**: Django项目核心配置目录
- **requirements.txt**: 项目依赖文件

### 2. 核心应用目录 (apps/)
- **meteorology**: 气象数据分析与监测
- **environment**: 环境质量监测与评估
- **resources**: 资源利用与管理
- **agriculture**: 农业生产与发展
- **population**: 人口统计与分析
- **dashboard**: 多维数据汇总与展示
- **ai_service**: AI模型服务与预测

### 3. 配置目录 (core/)
包含Django项目的核心配置文件，包括开发和生产环境的配置

### 4. 静态文件 (static/)
存放CSS、JavaScript、图表组件等静态资源

### 5. 模板文件 (templates/)
按模块分类存放HTML模板文件

### 6. 工具函数 (utils/)
包含各模块的数据处理工具和通用函数

### 7. 测试目录 (tests/)
包含所有模块的测试用例

### 8. 文档目录 (docs/)
存放项目文档、API文档等

### 9. 脚本目录 (scripts/)
存放各模块的数据导入导出脚本

### 10. 日志目录 (logs/)
存放应用程序的日志文件 