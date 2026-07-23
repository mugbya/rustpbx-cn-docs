# 安装部署


## 源码安装部署

### 依赖须知

- 要求 Rust 1.94.0 或更高版本
- Linux: apt-get install cmake pkg-config libasound2-dev libssl-dev libopus-dev
- macOS: brew install cmake openssl pkg-config

> 项目依赖的 sqlx 库（0.9.0 系列）要求 Rust 1.94.0 或更高版本

查看版本，评估是否需要升级
```bash
rustc --version
rustup update stable
```

### 安装部署

```bash
git clone https://github.com/restsend/rustpbx.git
cd rustpbx
cargo build --release
cargo run --bin rustpbx -- --conf config.toml.example
```

> 注意：让输入 https://cnb.cool 这个网站的账号密码，可以先结束，目前暂时不用子模块



## docker部署

```bash
docker run -d --name rustpbx --net host \
  -v $(pwd)/config.toml:/app/config.toml \
  ghcr.io/restsend/rustpbx:latest --conf /app/config.toml

# Create admin
docker exec rustpbx /app/rustpbx --conf /app/config.toml \
  --super-username admin --super-password changeme
```
