# 重新打镜像
相比于原镜像，改动点：
- 安装squoosh-cli，可在容器中使用该命令批量压缩图片
- 基于alpine:3.15构建镜像，验证发现node18使用squoosh-cli会报错，alpine:3.15中node为16版本

# 构建说明
- 下载源码`https://github.com/GoogleChromeLabs/squoosh`放置到当前目录，目前是2.0.0版本源码，非1.x版本的
- 使用当前目录下的package.json文件替换下载下来的源码中的package.json文件
- 构建镜像：`docker build -f ./Dockerfile_alpine3.15 -t dko0/squoosh:2.0.0 .`
