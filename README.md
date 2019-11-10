# 在 EdgeRouter X 里安装 frpc 客户端内网穿透
![](https://raw.githubusercontent.com/huangqian8/erx-frp/master/er-x.png)

SSH 连接 ERX，输入以下命令：

```
sudo -i
curl -L -O https://github.com/fatedier/frp/releases/download/v0.29.1/frp_0.29.1_linux_mipsle.tar.gz
tar -zxvf frp_0.29.1_linux_mipsle.tar.gz
cd frp_0.29.1_linux_mipsle
rm -rf frpc_full.ini
mkdir /config/scripts/frp
cp frpc* /config/scripts/frp
cp systemd/frpc.service /config/scripts/frp
ln -s /config/scripts/frp/frpc.service /etc/systemd/system/frpc.service
systemctl enable frpc && systemctl start frpc
```

#### P.S. 需要修改 frpc.ini 和 frpc.service 中的部分内容。
