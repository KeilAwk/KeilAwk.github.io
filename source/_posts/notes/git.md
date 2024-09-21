---
title: Git
date: 2024-09
note: true
tags:
---

## GPG&SSH
###命令
生成gpg秘钥:
```sh
gpg --full-generate-key
```

获取当前的私钥列表:
```sh
gpg --list-secret-keys --keyid-format=long
```

导出公钥(直接使用生成秘钥时返回的公钥id):
```sh
gpg --armor --export {id}
```

生成ssh秘钥:
```sh
ssh-keygen -t ed25519 -C {noreply-email}
```

## Git
###命令

快速设置:
```sh
git config --global user.name {}
git config --global user.email {}
git config --global commit.gpgsign true
```

clone单分支：
```sh
git clone --single-branch {repo} {dir}
```

检出分支(example)：
```sh
git checkout main
```

###加速git-bash

- 使用反代
  首先启动s302本地反代或watt toolkit的，启用github加速
  
  git全局设置(`git config --global --edit`)添加:
  ```config
  #此处`https`可换为`http`
  [https]
      proxy=https://127.0.0.1/
      sslBackend = schannel #使用系统证书服务
      sslVerify=true #默认为true，如果git无法使用系统证书才应禁用该项
  ```
- 使用镜像
  
  使用`git remote set-url origin https://kkgithub.com/{username}/{repo}`替换本地repo远程地址即可，kkgithub会自动转发
  
  镜像也可以用来辅助clone大仓库，完事了再改回origin即可


