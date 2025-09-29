基于Django和Vue的网络安全蜜罐系统
[信息安全][网络安全][2026新系统]
专门用于检测和记录网络攻击行为。系统有多种蜜罐类型：SSH、FTP、HTTP、Telnet、MySQL、Redis和Modbus等协议蜜罐，部署各种网络服务来诱捕攻击者。当攻击者尝试攻击/连接，系统会实时记录攻击日志，包括源IP、攻击类型、攻击数据等详细信息，并支持攻击行为的可视化分析和网络拓扑展示。
系统提供完整的Web管理界面，包括蜜罐的启动、停止、删除等生命周期管理，以及攻击日志的查询、分析和导出功能。支持用户权限管理和数据可视化。项目提供完整的测试脚本，包括SSH暴力破解测试、FTP连接测试等功能，帮助安全研究人员验证蜜罐的有效性和测试网络安全防护能力。

毕业设计-毕设-网络安全毕设-信息安全毕设-网络安全毕业设计-信息安全毕业设计-网安毕设-信安毕设-选题参考

演示视频：【网络安全蜜罐系统/工控蜜罐系统/网络安全/信息安全/网络安全毕设选题参考/网络安全毕业设计选题参考/信息安全毕设选题参考/Python/vue/MySQL】https://www.bilibili.com/video/BV1M8nzzZE9d?vd_source=97984b4127eb90a391d8becfdefc0e9e

# 网络安全蜜罐系统
可命名：网络安全蜜罐系统/工控蜜罐系统等等
一个基于Django + Vue.js的网络安全蜜罐管理系统，用于部署、监控和管理各种类型的蜜罐，实时检测和分析网络攻击。系统支持多种蜜罐类型，提供完整的攻击检测、日志记录和可视化分析功能。

## 系统架构

- **后端**: Django
- **前端**: Vue  ECharts
- **数据库**: MySQL 
- **测试工具**: Python测试脚本

## 功能特性

### 核心功能
- 🔐 用户认证和权限管理（基于Django用户系统）
- 🍯 蜜罐生命周期管理（创建、启动、停止、删除）
- 📊 实时攻击监控和统计仪表板
- 🌐 网络拓扑可视化（支持动态刷新）
- 📝 攻击日志记录和分析（支持严重程度分级）
- 🚨 安全告警和通知
- 🔧 管理后台

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




### 功能特性
- **多协议支持**: SSH、FTP、HTTP、Telnet、MySQL、Redis、Modbus
- **攻击模拟**: 暴力破解、端口扫描、协议攻击
- **结果分析**: 详细的测试报告和统计
- **日志记录**: 完整的测试过程日志
- **数据导出**: JSON格式的测试结果导出



### 监控和维护

- **数据库备份**：定期备份MySQL数据
- **日志监控**：监控系统日志和攻击日志
- **性能监控**：监控CPU、内存、磁盘使用情况
- **安全更新**：定期更新系统和依赖包
- **蜜罐维护**：定期检查蜜罐状态和配置



## 安全注意事项

- 定期更新系统和依赖包
- 使用强密码和密钥
- 限制网络访问权限
- 监控异常活动
- 定期备份重要数据

## 许可证

MIT License

## 贡献指南

本人开发
网络安全方向

## 联系方式

如有问题或建议，请通过以下方式联系：

- 邮箱: 1841109483@qq.com
- wechat: MrN1579












Network security honeypot system based on Django and Vue
[Information Security] [Network Security] [2026 New System]
Specially designed to detect and record network attack behavior. There are multiple types of honeypots in the system, including SSH, FTP, HTTP, Telnet, MySQL, Redis, Modbus, and other protocol honeypots. Various network services are deployed to trap attackers. When an attacker attempts to attack/connect, the system will record real-time attack logs, including detailed information such as source IP, attack type, and attack data, and support visual analysis of attack behavior and network topology display.
The system provides a complete web management interface, including lifecycle management such as starting, stopping, and deleting honeypots, as well as query, analysis, and export functions for attack logs. Support user permission management and data visualization. The project provides complete testing scripts, including SSH brute force cracking testing, FTP connection testing, and other functions, to help security researchers verify the effectiveness of honeypots and test network security protection capabilities.

Graduation Design - Graduation Design - Network Security Graduation Design - Information Security Graduation Design - Network Security Graduation Design - Information Security Graduation Design - Network Security Graduation Design - Information Security Graduation Design - Topic Reference

Demo video: [Network Security Honeypot System/Industrial Control Honeypot System/Network Security/Information Security/Network Security Graduation Design Topic Reference/Network Security Graduation Design Topic Reference/Information Security Graduation Design Topic Reference/Python/Vue/MySQL] https://www.bilibili.com/video/BV1M8nzzZE9d?vd_source=97984b4127eb90a391d8becfdefc0e9e

#Network security honeypot system
Naming options: Network Security Honeypot System/Industrial Control Honeypot System, etc
A network security honeypot management system based on Django+Vue.js, used for deploying, monitoring, and managing various types of honeypots, real-time detection and analysis of network attacks. The system supports multiple types of honeypots and provides complete attack detection, logging, and visual analysis functions.

##System architecture

-Backend: Django
-Front end: Vue ECharts
-* * Database * *: MySQL
-* * Testing Tool * *: Python Test Script

##Functional characteristics

###Core functions
-  🔐  User authentication and permission management (based on Django user system)
-  🍯  Honeypot Lifecycle Management (Create, Start, Stop, Delete)
-  📊  Real time attack monitoring and statistical dashboard
-  🌐  Network topology visualization (supports dynamic refresh)
-  📝  Attack log recording and analysis (supporting severity grading)
-  🚨  Security alerts and notifications
-  🔧  Admin Panel

###Honeypot type support
-SSH honeypot: Supports brute force cracking detection and records login attempts
-FTP Honeypot: Detection of File Transfer Protocol Attacks
-HTTP Honeypot: Web Application Attack Detection
-Telnet honeypot: Remote login attack detection
-MySQL Honeypot: Database Attack Detection
-Redis honeypot: Cache system attack detection
-Modbus Honeypot: Industrial Protocol Attack Detection

###Attack detection capability
-Violent cracking attacks: SSH, FTP, HTTP and other protocols
-Port scanning: Multi port scanning detection
-SQL Injection: Web Application SQL Injection Detection
-XSS attack: Cross site scripting attack detection
-Protocol attacks: Detection of attacks on various network protocols
-Abnormal behavior: Abnormal access pattern recognition




###Functional characteristics
-* * Multi protocol support * *: SSH, FTP, HTTP, Telnet, MySQL, Redis, Modbus
-Attack simulation: brute force cracking, port scanning, protocol attacks
-* * Result analysis * *: Detailed test report and statistics
-* * Log Record * *: Complete Test Process Log
-* * Data Export * *: Exporting test results in JSON format



###Monitoring and maintenance

-* * Database Backup * *: Regularly backup MySQL data
-* * Log Monitoring * *: Monitor system logs and attack logs
-* * Performance Monitoring * *: Monitor CPU, memory, and disk usage
-* * Security Update * *: Regularly update the system and dependency packages
-Honeypot Maintenance: Regularly check the status and configuration of the honeypot



##Safety precautions

-Regularly update the system and dependency packages
-Use strong passwords and keys
-Restricting network access permissions
-Monitor abnormal activity
-Regularly backup important data

##License

MIT License

##Contribution Guide

Developed by myself
Network Security Direction

##Contact Information

If you have any questions or suggestions, please contact us through the following methods:

-Email: 1841109483@qq.com
- wechat: MrN1579













