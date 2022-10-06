 - 服务器安装v2ray

      bash <(curl -L https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh)
      vi /usr/local/etc/v2ray/config.json
      systemctl start v2ray
      systemctl enable v2ray
      v2ray --config=/usr/local/etc/v2ray/config.json
      ufw allow 10086
      ufw allow 12107


- 服务器config.json

{
  "inbounds": [{
    "port": 12107,
    "listen":"65.20.96.27",
    "protocol": "vmess",
    "settings": {
      "clients": [
        {
          "id": "f3eaaa8f-b913-4cdc-a0a8-e257adc551e9"
        }
      ]
    }
  }],
  "outbounds": [{
    "protocol": "freedom",
    "settings": {
      "encryption":"none"
    }
  }]
}
