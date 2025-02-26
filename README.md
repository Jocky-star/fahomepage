# FAHomepage 项目文档

## 本地开发

### 环境要求
- Node.js 16+ (推荐16.20.0)
- npm 8+
- Git 2.30+

### 快速开始
```bash
# 克隆仓库
git clone https://github.com/Jocky-star/fahomepage.git
cd fahomepage

# 安装依赖
npm install

# 清理缓存（建议每次重新调试时先清理）
cmd /c "hexo clean"

# 生成静态文件
cmd /c "hexo generate"
# 或使用简写
cmd /c "hexo g"

# 启动开发服务器（支持实时预览）
cmd /c "hexo server"
# 或使用简写
cmd /c "hexo s"

# 如果需要指定端口和IP（推荐）
cmd /c "hexo s -p 4000 --ip 0.0.0.0"

# 一键清理、生成并启动服务器
cmd /c "hexo clean && hexo g && hexo s"
```

访问：http://localhost:4000

> 提示：开发服务器支持热重载，当你修改文件后会自动刷新页面。

## GitHub Pages 部署

### 配置要求
1. 修改 `_config.yml`：
```yaml
url: https://jocky-star.github.io/fahomepage
root: /fahomepage/

deploy:
  type: git
  repo: https://github.com/Jocky-star/fahomepage.git
  branch: gh-pages
```

2. 安装部署插件：
```bash
npm install hexo-deployer-git --save
```

### 部署命令
```bash
hexo clean && hexo generate && hexo deploy
```

## 服务器部署

### 直接运行
```bash
# 后台运行（4000端口）
nohup hexo server -p 4000 --ip 0.0.0.0 &
```

### Nginx配置示例
```nginx
server {
    listen 80;
    server_name yourdomain.com;
    
    location / {
        proxy_pass http://localhost:4000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

## Docker 部署

### 构建镜像
```bash
docker build -t fahomepage .
```

### 运行容器
```bash
docker run -d \
  -p 4000:4000 \
  --name homepage \
  fahomepage
```

## 常见问题

### 1. Node.js版本问题
```bash
# 使用n管理Node版本
npm install -g n
n 16.20.0
```

### 2. 插件加载失败
```bash
# 重新安装marked
npm install marked@4.3.0 --save
```

### 3. 端口冲突
```bash
# 使用不同端口启动
hexo server -p 5000 --ip 0.0.0.0
```

### 4. 样式文件加载失败
检查 `_config.yml` 的 `url` 和 `root` 配置是否与部署环境匹配

### 5. PowerShell 执行权限问题
如果遇到 "无法加载文件...因为在此系统上禁止运行脚本" 的错误，请尝试以下解决方案：

方案1 - 使用 cmd（推荐）：
```bash
# 切换到 cmd 运行
cmd /c "hexo clean"
cmd /c "hexo generate"
cmd /c "hexo server"
```

方案2 - 使用 npx：
```bash
npx hexo clean
npx hexo generate
npx hexo server
```

方案3 - 修改执行策略（不推荐）：
```bash
# 检查当前执行策略
Get-ExecutionPolicy -List

# 设置执行策略（以管理员身份运行）
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser -Force
```

---

> 最后更新：{{ now('YYYY-MM-DD') }}  
> 维护者：Future Array 团队