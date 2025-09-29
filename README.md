基于Django和Vue的网络安全蜜罐系统
[信息安全][网络安全][2026新系统]
专门用于检测和记录网络攻击行为。系统有多种蜜罐类型：SSH、FTP、HTTP、Telnet、MySQL、Redis和Modbus等协议蜜罐，部署各种网络服务来诱捕攻击者。当攻击者尝试攻击/连接，系统会实时记录攻击日志，包括源IP、攻击类型、攻击数据等详细信息，并支持攻击行为的可视化分析和网络拓扑展示。
系统提供完整的Web管理界面，包括蜜罐的启动、停止、删除等生命周期管理，以及攻击日志的查询、分析和导出功能。支持用户权限管理和数据可视化。项目提供完整的测试脚本，包括SSH暴力破解测试、FTP连接测试等功能，帮助安全研究人员验证蜜罐的有效性和测试网络安全防护能力。



# 网络安全蜜罐系统

一个基于Django + Vue.js的网络安全蜜罐管理系统，用于部署、监控和管理各种类型的蜜罐，实时检测和分析网络攻击。系统支持多种蜜罐类型，提供完整的攻击检测、日志记录和可视化分析功能。

## 系统架构

- **后端**: Django 5.2 + Django REST Framework + SimpleUI
- **前端**: Vue 3 + Element Plus + ECharts
- **数据库**: MySQL 8.0
- **容器化**: Docker + Docker Compose
- **Web服务器**: Nginx
- **测试工具**: Python测试脚本套件

## 功能特性

### 核心功能
- 🔐 用户认证和权限管理（基于Django用户系统）
- 🍯 蜜罐生命周期管理（创建、启动、停止、删除）
- 📊 实时攻击监控和统计仪表板
- 🌐 网络拓扑可视化（支持动态刷新）
- 📝 攻击日志记录和分析（支持严重程度分级）
- 🚨 安全告警和通知
- 🔧 管理后台（基于SimpleUI）

### 蜜罐类型支持
- **SSH蜜罐**: 支持暴力破解检测，记录登录尝试
- **FTP蜜罐**: 文件传输协议攻击检测
- **HTTP蜜罐**: Web应用攻击检测
- **Telnet蜜罐**: 远程登录攻击检测
- **MySQL蜜罐**: 数据库攻击检测
- **Redis蜜罐**: 缓存系统攻击检测
- **Modbus蜜罐**: 工业协议攻击检测

### 攻击检测能力
- **暴力破解攻击**: SSH、FTP、HTTP等协议
- **端口扫描**: 多端口扫描检测
- **SQL注入**: Web应用SQL注入检测
- **XSS攻击**: 跨站脚本攻击检测
- **协议攻击**: 各种网络协议的攻击检测
- **异常行为**: 非正常访问模式识别

## 快速开始

### 方式一：本地开发（推荐）

#### 环境要求
- Python 3.8+
- Node.js 14+
- MySQL 8.0
- Docker（用于蜜罐容器）

#### 启动后端服务

1. 进入后端目录：
   ```bash
   cd myproject
   ```

2. 创建虚拟环境：
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   # 或
   venv\Scripts\activate     # Windows
   ```

3. 安装Python依赖：
   ```bash
   pip install -r requirements.txt
   ```

4. 配置数据库（MySQL）：
   - 创建数据库：`py_docker_honeypot`
   - 修改`settings.py`中的数据库配置：
   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'py_docker_honeypot',
           'USER': 'root',
           'PASSWORD': '123456',
           'HOST': 'localhost',
           'PORT': '3306',
       }
   }
   ```

5. 执行数据库迁移：
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. 创建超级用户：
   ```bash
   python manage.py createsuperuser
   ```

7. 启动服务：
   ```bash
   python manage.py runserver
   ```

#### 启动前端服务

1. 进入前端目录：
   ```bash
   cd my-vue-project
   ```

2. 安装依赖：
   ```bash
   npm install
   ```

3. 启动开发服务器：
   ```bash
   npm run serve
   ```

#### 访问系统
- **前端界面**: http://localhost:3000
- **后端API**: http://localhost:8000
- **管理后台**: http://localhost:8000/admin
- **API文档**: http://localhost:8000/api/

### 方式二：使用Docker（生产环境）

1. 确保已安装Docker和Docker Compose
2. 构建和启动服务：
   ```bash
   docker-compose up -d
   ```
3. 访问系统：
   - 前端界面: http://localhost:3000
   - 后端API: http://localhost:8000
   - 管理后台: http://localhost:8000/admin

## 系统配置

### 数据库配置

系统使用MySQL作为主数据库，在`myproject/myproject/settings.py`中配置：

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'py_docker_honeypot',
        'USER': 'root',
        'PASSWORD': '123456',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 时区和语言配置

```python
LANGUAGE_CODE = 'zh-hans'
TIME_ZONE = 'Asia/Shanghai'
USE_I18N = True
USE_TZ = True
```

### SimpleUI管理后台配置

```python
SIMPLEUI_HOME_INFO = False
SIMPLEUI_ANALYSIS = False
SIMPLEUI_DEFAULT_THEME = 'dark-green.css'
SIMPLEUI_STATIC_OFFLINE = True
SIMPLEUI_SEARCH_ENABLED = True
SIMPLEUI_HOME_TITLE = '蜜罐管理控制台'
```

### CORS跨域配置

```python
CORS_ALLOW_ALL_ORIGINS = True
CORS_ALLOW_CREDENTIALS = True
CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
    "http://127.0.0.1:3000",
]
```

## API接口文档

### 认证接口
- `POST /api/auth/login/` - 用户登录
- `POST /api/auth/logout/` - 用户登出
- `POST /api/auth/register/` - 用户注册

### 蜜罐管理接口
- `GET /api/honeypots/` - 获取蜜罐列表
- `POST /api/honeypots/` - 创建蜜罐
- `GET /api/honeypots/{id}/` - 获取蜜罐详情
- `PUT /api/honeypots/{id}/` - 更新蜜罐
- `DELETE /api/honeypots/{id}/` - 删除蜜罐
- `POST /api/honeypots/{id}/start/` - 启动蜜罐
- `POST /api/honeypots/{id}/stop/` - 停止蜜罐

### 攻击日志接口
- `GET /api/attacks/` - 获取攻击日志
- `GET /api/attacks/{id}/` - 获取攻击详情
- `GET /api/attacks/stats/` - 获取攻击统计

### 拓扑接口
- `GET /api/topology/` - 获取网络拓扑数据

### 仪表板接口
- `GET /api/dashboard/stats/` - 获取仪表板统计数据
- `GET /api/dashboard/attacks/` - 获取攻击趋势数据

## 测试工具

### 蜜罐测试脚本

系统提供了完整的测试工具套件，位于`tests_honeypot/`目录：

#### SSH蜜罐测试
```bash
# 基础SSH连接测试
python tests_honeypot/quick_ssh_test.py

# 完整SSH攻击模拟
python tests_honeypot/simulate_ssh_attack.py

# SSH蜜罐功能测试
python tests_honeypot/test_ssh_honeypot.py
```

#### FTP蜜罐测试
```bash
# FTP蜜罐测试
python tests_honeypot/test_ftp_honeypot.py

# 快速FTP测试
python tests_honeypot/quick_ftp_test.py
```

#### 其他协议测试
```bash
# Telnet蜜罐测试
python tests_honeypot/quick_telnet_test.py

# MySQL蜜罐测试
python tests_honeypot/test_real_mysql_honeypot.py

# Redis蜜罐测试
python tests_honeypot/test_redis_honeypot.py

# Modbus蜜罐测试
python tests_honeypot/test_modbus_honeypot.py
```

### 测试功能特性
- **多协议支持**: SSH、FTP、HTTP、Telnet、MySQL、Redis、Modbus
- **攻击模拟**: 暴力破解、端口扫描、协议攻击
- **结果分析**: 详细的测试报告和统计
- **日志记录**: 完整的测试过程日志
- **数据导出**: JSON格式的测试结果导出

## 部署说明

### 生产环境部署

1. **环境准备**：
   - 安装Docker和Docker Compose
   - 配置MySQL数据库
   - 设置防火墙规则

2. **数据库配置**：
   ```sql
   CREATE DATABASE py_docker_honeypot CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   CREATE USER 'honeypot'@'localhost' IDENTIFIED BY 'your_secure_password';
   GRANT ALL PRIVILEGES ON py_docker_honeypot.* TO 'honeypot'@'localhost';
   FLUSH PRIVILEGES;
   ```

3. **Docker部署**：
   ```bash
   # 构建镜像
   docker-compose build
   
   # 启动服务
   docker-compose up -d
   
   # 查看日志
   docker-compose logs -f
   ```

4. **SSL配置**：
   - 申请SSL证书
   - 配置Nginx反向代理
   - 启用HTTPS访问

### 监控和维护

- **数据库备份**：定期备份MySQL数据
- **日志监控**：监控系统日志和攻击日志
- **性能监控**：监控CPU、内存、磁盘使用情况
- **安全更新**：定期更新系统和依赖包
- **蜜罐维护**：定期检查蜜罐状态和配置

## 开发指南

### 项目结构

```
py_docker_honeypot/
├── myproject/                    # Django后端
│   ├── honeypot/                # 蜜罐应用
│   │   ├── models.py           # 数据模型
│   │   ├── admin.py            # 管理后台
│   │   ├── serializers.py      # API序列化器
│   │   ├── views.py            # API视图
│   │   └── management/          # 管理命令
│   ├── myproject/              # 项目配置
│   │   ├── settings.py         # 配置文件
│   │   └── urls.py             # URL路由
│   ├── requirements.txt        # Python依赖
│   └── manage.py
├── my-vue-project/              # Vue前端
│   ├── src/
│   │   ├── views/              # 页面组件
│   │   │   ├── Dashboard.vue   # 仪表板
│   │   │   ├── HoneypotList.vue # 蜜罐列表
│   │   │   ├── AttackLogs.vue  # 攻击日志
│   │   │   └── TopologyView.vue # 网络拓扑
│   │   ├── components/         # 通用组件
│   │   ├── api/                # API接口
│   │   └── router/             # 路由配置
│   └── package.json
├── tests_honeypot/              # 测试工具
│   ├── test_ssh_honeypot.py    # SSH测试
│   ├── test_ftp_honeypot.py    # FTP测试
│   ├── simulate_ssh_attack.py # 攻击模拟
│   └── quick_ssh_test.py       # 快速测试
└── README.md
```

### 数据模型

#### HoneypotType（蜜罐类型）
- `name`: 类型名称
- `description`: 描述
- `docker_image`: Docker镜像
- `port`: 端口号

#### Honeypot（蜜罐实例）
- `name`: 蜜罐名称
- `honeypot_type`: 蜜罐类型
- `container_id`: 容器ID
- `status`: 状态（运行中/已停止/错误/启动中）
- `ip_address`: IP地址
- `port`: 端口
- `created_by`: 创建者

#### AttackLog（攻击日志）
- `honeypot`: 关联蜜罐
- `attack_type`: 攻击类型
- `source_ip`: 源IP
- `attack_data`: 攻击数据
- `severity`: 严重程度
- `timestamp`: 时间戳

### 添加新的蜜罐类型

1. **后端开发**：
   ```python
   # 在 honeypot/models.py 中添加新类型
   class NewHoneypotType(HoneypotType):
       # 添加特定字段
       pass
   ```

2. **API接口**：
   ```python
   # 在 honeypot/views.py 中实现API
   class NewHoneypotViewSet(viewsets.ModelViewSet):
       # 实现CRUD操作
       pass
   ```

3. **前端组件**：
   ```vue
   <!-- 在 my-vue-project/src/views/ 中添加新页面 -->
   <template>
     <!-- 新蜜罐类型的管理界面 -->
   </template>
   ```

### 自定义攻击检测规则

1. **检测器开发**：
   ```python
   # 在 honeypot/detectors/ 中创建检测器
   class CustomDetector:
       def detect(self, data):
           # 实现检测逻辑
           return result
   ```

2. **规则配置**：
   ```python
   # 在蜜罐配置中启用检测器
   DETECTION_RULES = {
       'custom_detector': {
           'enabled': True,
           'threshold': 0.8
       }
   }
   ```

### 前端开发

#### 组件开发
```vue
<template>
  <div class="component">
    <!-- 组件模板 -->
  </div>
</template>

<script>
export default {
  name: 'ComponentName',
  data() {
    return {
      // 组件数据
    }
  },
  methods: {
    // 组件方法
  }
}
</script>
```

#### API调用
```javascript
// 在 src/api/index.js 中添加API方法
export const honeypotAPI = {
  getHoneypots: () => axios.get('/api/honeypots/'),
  createHoneypot: (data) => axios.post('/api/honeypots/', data),
  // 其他API方法
}
```

## 安全注意事项

- 定期更新系统和依赖包
- 使用强密码和密钥
- 限制网络访问权限
- 监控异常活动
- 定期备份重要数据

## 许可证

MIT License

## 贡献指南

1. Fork 项目
2. 创建功能分支
3. 提交更改
4. 推送到分支
5. 创建 Pull Request

## 联系方式

如有问题或建议，请通过以下方式联系：

- 邮箱: 1841109483@qq.com
- wechat: MrN1579
## 更新日志

### v1.0.0 (2024-01-01)
- 初始版本发布
- 支持基础蜜罐管理功能
- 实现攻击检测和日志记录
- 提供Web管理界面





nmap -p 2222 --script ssh-brute --script-args userdb=/usr/share/wordlists/metasploit/unix_users.txt,passdb=/usr/share/wordlists/rockyou.txt 192.168.64.209
