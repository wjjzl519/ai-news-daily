# AI资讯日报 (AI News Daily)
https://wjjzl519.github.io/ai-news-daily/
## 项目简介

AI资讯日报是一个基于现代云原生技术栈的自动化AI新闻聚合系统。该项目通过整合 **Cloudflare Workers**、**DeepSeek AI** 和 **GitHub Actions** 等先进技术，实现每日自动获取、分析和推送全球最新AI科技资讯的功能。

## 🚀 核心特性

### 📰 智能新闻聚合
- **多源采集**: 从全球主流科技媒体和AI专业网站自动抓取最新资讯
- **AI驱动**: 利用DeepSeek先进的AI模型进行内容理解和筛选
- **实时更新**: 每日定时自动更新，确保信息时效性

### 🤖 AI增强处理
- **智能摘要**: 使用DeepSeek AI自动生成新闻摘要和关键信息提取
- **内容分类**: 自动对新闻进行主题分类和重要性评级
- **去重过滤**: 智能识别和合并重复或相似内容

### ☁️ 无服务器架构
- **Cloudflare Workers**: 利用边缘计算实现高性能、低延迟的数据处理
- **全球分发**: 基于Cloudflare的全球CDN网络，确保世界各地访问速度
- **成本优化**: 无服务器架构，按需付费，大幅降低运维成本

### 🔄 自动化工作流
- **GitHub Actions**: 完全自动化的CI/CD流水线
- **定时任务**: 支持灵活的调度配置
- **版本控制**: 所有内容变更都有完整的Git历史记录

## 🏗️ 技术架构

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   数据源采集     │────│  Cloudflare      │────│   AI内容处理     │
│   (RSS/API)     │    │  Workers         │    │   (DeepSeek)    │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                        │                        │
         │                        │                        │
         ▼                        ▼                        ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  GitHub Actions │────│   内容存储与      │────│    用户界面      │
│   (自动化调度)   │    │   版本管理       │    │   (GitHub Pages) │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

### 技术栈详解

#### 🔧 后端服务
- **Cloudflare Workers**: 边缘计算平台，处理API请求和数据转换
- **DeepSeek AI**: 提供自然语言处理和内容理解能力
- **GitHub API**: 用于内容存储和版本管理

#### 🔄 自动化
- **GitHub Actions**: 实现定时任务和CI/CD流水线
- **Cron调度**: 支持灵活的时间配置
- **工作流编排**: 多步骤自动化处理流程

#### 📊 数据处理
- **RSS解析**: 支持多种RSS/Atom源格式
- **API集成**: 对接主流新闻API服务
- **数据清洗**: 自动去除广告和无关内容

## 📋 功能特性

### 新闻聚合功能
- ✅ 多平台新闻源整合
- ✅ 智能内容去重
- ✅ 关键词提取和标签化
- ✅ 趋势分析和热点识别

### AI增强功能
- ✅ 自动摘要生成
- ✅ 情感分析
- ✅ 重要性评分
- ✅ 相关文章推荐

### 用户体验
- ✅ 响应式网页设计
- ✅ 移动端适配
- ✅ RSS订阅支持
- ✅ 多语言支持

## 🚀 快速开始

### 环境要求
- Node.js 18+
- GitHub账号
- Cloudflare账号
- DeepSeek API密钥

### 部署步骤

1. **Fork 仓库**
   ```bash
   # 克隆项目到本地
   git clone https://github.com/wjjzl519/ai-news-daily.git
   cd ai-news-daily
   ```

2. **配置环境变量**
   在GitHub repository的Settings → Secrets中添加：
   ```
   CLOUDFLARE_API_TOKEN=your_cloudflare_api_token
   DEEPSEEK_API_KEY=your_deepseek_api_key
   GITHUB_TOKEN=your_github_token
   ```

3. **部署Workers**
   ```bash
   # 安装依赖
   npm install
   
   # 部署到Cloudflare Workers
   npm run deploy
   ```

4. **启用GitHub Actions**
   - 在Actions页面启用工作流
   - 配置定时任务时间

## ⚙️ 配置说明

### 新闻源配置
在`config/sources.json`中配置新闻源：
```json
{
  "sources": [
    {
      "name": "TechCrunch",
      "url": "https://techcrunch.com/feed/",
      "type": "rss",
      "category": "tech"
    }
  ]
}
```

### AI处理配置
在`config/ai.json`中配置AI参数：
```json
{
  "model": "deepseek-chat",
  "temperature": 0.3,
  "max_tokens": 2000,
  "summary_length": 200
}
```

## 📈 性能优势

### 速度与可靠性
- **全球CDN**: Cloudflare的200+个数据中心确保全球访问速度
- **边缘计算**: 请求在最近的边缘节点处理，延迟最小化
- **高可用性**: 99.9%以上的服务可用时间保障

### 成本效益
- **按需付费**: Cloudflare Workers按请求计费，无固定成本
- **免费额度**: 每日100,000次免费请求额度
- **资源优化**: 智能缓存和压缩减少带宽消耗

## 🔧 自定义开发

### 添加新的新闻源
1. 在`src/sources/`目录下创建新的源处理器
2. 实现标准的接口方法
3. 在配置文件中注册新源

### 扩展AI功能
1. 在`src/ai/`目录下添加新的处理模块
2. 集成DeepSeek的其他模型能力
3. 配置相应的提示词模板

### 自定义输出格式
1. 修改`src/formatters/`中的格式化器
2. 支持多种输出格式（JSON、Markdown、HTML等）
3. 添加自定义模板支持

## 🤝 贡献指南

我们欢迎所有形式的贡献！

### 贡献方式
- 🐛 报告Bug和问题
- 💡 提出新功能建议
- 📝 改进文档
- 🔧 提交代码修复和新特性

### 开发流程
1. Fork项目仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建Pull Request

## 📄 许可证

本项目采用 MIT 许可证。详情请查看 [LICENSE](LICENSE) 文件。

## 🙋‍♂️ 常见问题

### Q: 如何修改新闻更新频率？
A: 在`.github/workflows/daily-news.yml`中修改cron表达式。

### Q: 支持哪些新闻源格式？
A: 目前支持RSS、Atom、JSON Feed和REST API格式。

### Q: 如何自定义AI处理逻辑？
A: 可以在`src/ai/processors/`目录下创建自定义处理器。

### Q: 项目的运行成本是多少？
A: 基于Cloudflare Workers的免费额度，中小规模使用基本免费。

## 📞 联系我们

- 项目主页: [GitHub Repository](https://github.com/wjjzl519/ai-news-daily)
- 问题反馈: [GitHub Issues](https://github.com/wjjzl519/ai-news-daily/issues)
- 功能请求: [GitHub Discussions](https://github.com/wjjzl519/ai-news-daily/discussions)

---

*使用现代技术栈，让AI资讯触手可及。*
