# MajsoulMax

本项目是 [MajsoulMax](https://github.com/Avenshy/MajsoulMax) 的一个修改版，主要为了适配 [Majsoul Helper](https://github.com/zhuozhiyongde/MajsoulHelper) 项目的容器化部署。

## ✨ 核心修改

1.  **增加 HTTP Auth**：增加 HTTP Auth 认证，方便服务器部署使用。
2.  **增加 Vendor 依赖管理**：兼容与 Akagi 共用环境。

## 🚀 使用方式

参见 [原项目 README](https://github.com/Avenshy/MajsoulMax/) 与 [这篇博文](https://arthals.ink/blog/majsoul)。

入口鉴权：可选通过环境变量 `PROXY_USERNAME` 和 `PROXY_PASSWORD` 设置代理认证用户名和密码。

独立启动：

```bash
pip install -r requirements.txt
mitmdump -p 23410 -s addons.py
```

适配 Akagi 启动：

```bash
pip install --target ./vendor protobuf==3.20.1 --no-dependencies
mitmdump -p 23410 --mode upstream:http://akagi:7880 -s addons.py --ssl-insecure
```

## 📜 许可证

本项目基于 [GNU General Public License v3.0](./LICENSE) 许可证开源。