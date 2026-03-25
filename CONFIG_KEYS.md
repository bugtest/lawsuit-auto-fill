# 配置密钥说明

## 腾讯云 OCR 密钥配置

### 方式一：命令行参数（推荐）
```bash
python3 src/lawsuit_filler.py \
    -p 证据.pdf -t 模板.docx -o 输出.docx \
    --ocr-mode tencent \
    --tencent-secret-id YOUR_SECRET_ID \
    --tencent-secret-key YOUR_SECRET_KEY
```

### 方式二：配置文件
编辑 `config/config.yaml`：
```yaml
tencent:
  secret_id: YOUR_TENCENT_SECRET_ID
  secret_key: YOUR_TENCENT_SECRET_KEY
  region: ap-guangzhou
```

### 方式三：环境变量
```bash
export TENCENT_SECRET_ID=YOUR_SECRET_ID
export TENCENT_SECRET_KEY=YOUR_SECRET_KEY
```

---

## 阿里云百炼 API Key 配置

### 方式一：命令行参数
```bash
python3 src/lawsuit_filler.py \
    -p 证据.pdf -t 模板.docx -o 输出.docx \
    --extract-mode llm \
    --llm-api-key YOUR_DASHSCOPE_API_KEY
```

### 方式二：配置文件
编辑 `config/config.yaml`：
```yaml
llm:
  api_key: YOUR_DASHSCOPE_API_KEY
```

---

## ⚠️ 安全提醒

1. **不要将真实密钥提交到 Git**
   - config.yaml 已使用占位符
   - 真实密钥保存在本地

2. **建议使用环境变量**
   ```bash
   # ~/.bashrc 或 ~/.zshrc
   export TENCENT_SECRET_ID=xxx
   export TENCENT_SECRET_KEY=xxx
   export DASHSCOPE_API_KEY=xxx
   ```

3. **定期检查密钥轮换**

---

## 获取密钥

### 腾讯云 OCR
1. 登录 https://console.cloud.tencent.com/
2. 访问 CAM 控制台 → API 密钥管理
3. 创建或查看现有密钥

### 阿里云百炼
1. 登录 https://dashscope.console.aliyun.com/
2. 访问 API-KEY Management
3. 创建或查看现有密钥
