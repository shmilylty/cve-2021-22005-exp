# cve-2021-22005-exp

## 0x01 漏洞简介
2021年9月21日，VMware发布安全公告，公开披露了vCenter Server中的19个安全漏洞，这些漏洞的CVSSv3评分范围为4.3-9.8。

其中，最为严重的漏洞为vCenter Server 中的任意文件上传漏洞(CVE-2021-22005)，该漏洞存在于vCenter Server的分析服务中，其CVSSv3评分为 9.8。能够网络访问vCenter Server 上的 443 端口的攻击者可以通过上传恶意文件在 vCenter Server 上远程执行代码。该漏洞无需经过身份验证即可远程利用，攻击复杂度低，且无需用户交互。

## 0x02 影响范围

* vCenter Server 7.0 < 7.0 U2c build-18356314
* vCenter Server 6.7 < 6.7 U3o build-18485166
* Cloud Foundation (vCenter Server) 4.x < KB85718 (4.3)
* Cloud Foundation (vCenter Server) 3.x < KB85719 (3.10.2.2)

6.7 vCenters Windows版本不受影响

## 0x03 漏洞分析

https://xz.aliyun.com/t/10524

https://testbnull.medium.com/quick-note-of-vcenter-rce-cve-2021-22005-4337d5a817ee

## 0x04 使用说明

注意：本exp只能打目标为Linux版本的vCenter。

**帮助说明** 

```
usage: exp [-h] -t TARGET [-s SHELL] [-p PROXY]

optional arguments:
  -h, --help            show this help message and exit
  -t TARGET, --target TARGET
                        target url(e.g. https://192.168.1.1)
  -s SHELL, --shell SHELL
                        local webshell file path(default cmd.jsp)
  -p PROXY, --proxy PROXY
                        request proxy(e.g. http://127.0.0.1:1080)
```

本exp已对目标版本VMware vCenter Server 7.0.0 build-16323968测试通过。

![image](https://user-images.githubusercontent.com/24275308/147064895-afaf7b76-d638-476d-86d1-c59cd2b8c79a.png)
