# 环境与人类发展大数据分析平台数据库设计字典

## 1. 气象数据库表设计

### 1.1 气温记录表 (meteorology_temperature)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| station_id | varchar | 50 | 否 | - | 气象站编号 |
| temperature | decimal | (5,2) | 否 | - | 温度值(℃) |
| humidity | decimal | (5,2) | 是 | - | 湿度(%) |
| measurement_time | datetime | - | 否 | - | 测量时间 |
| location | point | - | 否 | - | 地理位置 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 1.2 降水量表 (meteorology_precipitation)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| station_id | varchar | 50 | 否 | - | 气象站编号 |
| precipitation | decimal | (8,2) | 否 | - | 降水量(mm) |
| precipitation_type | varchar | 20 | 是 | - | 降水类型 |
| measurement_time | datetime | - | 否 | - | 测量时间 |
| location | point | - | 否 | - | 地理位置 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 1.3 空气质量表 (meteorology_air_quality)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| station_id | varchar | 50 | 否 | - | 监测站编号 |
| pm25 | decimal | (6,2) | 是 | - | PM2.5浓度 |
| pm10 | decimal | (6,2) | 是 | - | PM10浓度 |
| aqi | int | 11 | 否 | - | 空气质量指数 |
| measurement_time | datetime | - | 否 | - | 测量时间 |
| location | point | - | 否 | - | 地理位置 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

## 2. 环境数据库表设计

### 2.1 污染物监测表 (environment_pollutant)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| station_id | varchar | 50 | 否 | - | 监测站编号 |
| pollutant_type | varchar | 50 | 否 | - | 污染物类型 |
| concentration | decimal | (10,4) | 否 | - | 污染物浓度 |
| unit | varchar | 20 | 否 | - | 计量单位 |
| measurement_time | datetime | - | 否 | - | 测量时间 |
| location | point | - | 否 | - | 地理位置 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 2.2 水质监测表 (environment_water_quality)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| station_id | varchar | 50 | 否 | - | 监测站编号 |
| ph_value | decimal | (4,2) | 否 | - | pH值 |
| dissolved_oxygen | decimal | (5,2) | 否 | - | 溶解氧(mg/L) |
| cod | decimal | (6,2) | 否 | - | 化学需氧量 |
| measurement_time | datetime | - | 否 | - | 测量时间 |
| water_body_type | varchar | 50 | 否 | - | 水体类型 |
| location | point | - | 否 | - | 地理位置 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

## 3. 资源数据库表设计

### 3.1 水资源表 (resources_water)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| region_id | varchar | 50 | 否 | - | 区域编号 |
| water_type | varchar | 50 | 否 | - | 水资源类型 |
| volume | decimal | (12,2) | 否 | - | 水资源量(万立方米) |
| usage_type | varchar | 50 | 否 | - | 使用类型 |
| measurement_time | datetime | - | 否 | - | 统计时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 3.2 土地资源表 (resources_land)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| region_id | varchar | 50 | 否 | - | 区域编号 |
| land_type | varchar | 50 | 否 | - | 土地类型 |
| area | decimal | (12,2) | 否 | - | 面积(平方公里) |
| usage_type | varchar | 50 | 否 | - | 使用类型 |
| measurement_time | datetime | - | 否 | - | 统计时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

## 4. 农业数据库表设计

### 4.1 农作物产量表 (agriculture_crop_yield)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| region_id | varchar | 50 | 否 | - | 区域编号 |
| crop_type | varchar | 50 | 否 | - | 作物类型 |
| yield | decimal | (12,2) | 否 | - | 产量(吨) |
| planting_area | decimal | (10,2) | 否 | - | 种植面积(公顷) |
| harvest_time | datetime | - | 否 | - | 收获时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 4.2 耕地信息表 (agriculture_farmland)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| region_id | varchar | 50 | 否 | - | 区域编号 |
| land_quality | varchar | 20 | 否 | - | 土地质量等级 |
| area | decimal | (10,2) | 否 | - | 面积(公顷) |
| irrigation_type | varchar | 50 | 是 | - | 灌溉类型 |
| soil_type | varchar | 50 | 否 | - | 土壤类型 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

## 5. 人口数据库表设计

### 5.1 人口统计表 (population_statistics)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| region_id | varchar | 50 | 否 | - | 区域编号 |
| total_population | int | 11 | 否 | - | 总人口数 |
| gender_ratio | decimal | (5,2) | 否 | - | 性别比例 |
| age_structure | json | - | 否 | - | 年龄结构 |
| education_level | json | - | 否 | - | 教育水平分布 |
| statistical_time | datetime | - | 否 | - | 统计时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 5.2 人口流动表 (population_migration)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| source_region | varchar | 50 | 否 | - | 来源地区 |
| target_region | varchar | 50 | 否 | - | 目标地区 |
| migration_population | int | 11 | 否 | - | 流动人口数 |
| migration_type | varchar | 50 | 否 | - | 流动类型 |
| migration_reason | varchar | 100 | 是 | - | 流动原因 |
| statistical_time | datetime | - | 否 | - | 统计时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

## 6. 系统管理表设计

### 6.1 用户管理表 (system_user)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| username | varchar | 50 | 否 | - | 用户名 |
| password | varchar | 255 | 否 | - | 密码(加密) |
| email | varchar | 100 | 否 | - | 电子邮箱 |
| role | varchar | 20 | 否 | 'user' | 角色 |
| status | tinyint | 4 | 否 | 1 | 状态(1:启用,0:禁用) |
| last_login | datetime | - | 是 | - | 最后登录时间 |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 |
| updated_at | datetime | - | 否 | CURRENT_TIMESTAMP | 更新时间 |

### 6.2 操作日志表 (system_operation_log)
| 字段名 | 类型 | 长度 | 允许空 | 默认值 | 说明 |
|--------|------|------|--------|--------|------|
| id | bigint | 20 | 否 | 自增 | 主键 |
| user_id | bigint | 20 | 否 | - | 用户ID |
| operation_type | varchar | 50 | 否 | - | 操作类型 |
| operation_content | text | - | 否 | - | 操作内容 |
| ip_address | varchar | 50 | 否 | - | IP地址 |
| operation_time | datetime | - | 否 | CURRENT_TIMESTAMP | 操作时间 |
| status | tinyint | 4 | 否 | 1 | 状态(1:成功,0:失败) |
| created_at | datetime | - | 否 | CURRENT_TIMESTAMP | 创建时间 | 