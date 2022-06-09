## 编辑未完成，图片文字排版更新中。

# 21.6.13：更新要点

几乎推倒重建的更新！

1、加入Centos/Debain系统的支持

![712b6861802a55597e161caa59adc0a](https://user-images.githubusercontent.com/80431714/121798581-c4275600-cc59-11eb-97f5-fe7f8be7a9fd.png)

![f9b35ccf3fd333c83e95ae6b660ddcb](https://user-images.githubusercontent.com/80431714/121798610-e7ea9c00-cc59-11eb-8774-e3d36aabd978.png)


2、自动识别系统，无须手动输入专用IP与IPV6

3、内核更新独立选择

![644a40002abdabac007fb10fc3a8c6e](https://user-images.githubusercontent.com/80431714/121798587-cc7f9100-cc59-11eb-981d-3e0e31f3b4b3.png)


4、更智能得检测当前正使用哪个V4或V6地址

![21cf70a6bd155b549b7839bddd0280e](https://user-images.githubusercontent.com/80431714/121798598-d4d7cc00-cc59-11eb-8add-1ccc6756ad13.png)


### 更新已测试通过的VPS名单：oracle，buyvm，gpc………………,欢迎大家补充反馈，相关视频教程下期发布………

--------------------------------------------------------------------------------------------
## 针对KVM架构VPS的WARP一键综合脚本
- [x] 支持自动识别X86与ARM的CPU架构
- [x] 支持 纯IPV4  VPS
- [x] 支持 IPV4+IPV6双栈VPS
- [x] 支持 纯IPV6  VPS（目前仅Ubuntu后续会更新）
- [x] 支持 Ubuntu/Centos/Debain系统！！！

![d89ed915a4e612e87946206873184a8](https://user-images.githubusercontent.com/80431714/121798546-9b9f5c00-cc59-11eb-8b6e-e3462ce7c6ec.png)

### OpenVZ、LXC架构VPS脚本:[EUserv 纯ipv6(OpenVZ、LXC架构VPS)WARP项目](https://github.com/YG-tsj/EUserv-warp)后续也将更新。
-----------------------------------------------------------------------------------------
# 目录

* [root一键脚本](#root一键脚本)

* [vps的ip套上warp功能的优势及不足](#vps的ip套上warp功能的优势及不足)

* [warp多功能一键脚本](#warp多功能一键脚本)

* [warp多功能一键脚本各功能简析](#warp多功能一键脚本各功能简析)

* [自定义ip分流配置模板说明](#自定义ip分流配置模板说明)

* [相关附加说明](#相关附加说明)
-----------------------------------------------------------------------------------------
### 相关视频教程及项目

- [纯IPV4 VPS添加WARP 如何查看专用IP地址](https://youtu.be/o7e_ikV-m-g)
- [甲骨文添加真IPV6，如何选择WARP脚本看奈非](https://youtu.be/ap_krqWnikE)
- [EUserv 纯ipv6(OpenVZ、LXC架构VPS)WARP项目](https://github.com/YG-tsj/EUserv-warp)
---------------------------------------------------------------------------------------------
### root一键脚本

用户名：root，密码自定义。方便登录与编辑文件！！后续再次执行脚本意味着更改root密码！！

提示：密码不要设置得过于简单，容易被破解。密钥文件要保存好，以防万一！

- **脚本一：适用于纯IPV4 VPS与IPV4+IPV6双栈VPS，非root状态下直接输入以下脚本（支持甲骨文与谷歌云）**

```
bash <(curl -sSL https://raw.githubusercontent.com/YG-tsj/Pro-warp/main/root.sh)
```

- **脚本二：适用于纯IPV6 VPS，先执行```sudo -i```进入root模式后再输入以下脚本（已集成永久DNS64）**

```
echo -e nameserver 2a00:1098:2c::1 > /etc/resolv.conf && bash <(curl -sSL https://raw.githubusercontent.com/YG-tsj/Pro-warp/main/v6root.sh)
```

-----------------------------------------------------------------------------------------
### vps的ip套上warp功能的优势及不足

<details>
<summary>给纯IPV4/纯IPV6 VPS添加WARP的好处</summary>

```bash
1：使只有IPV4/IPV6的VPS获取访问IPV6/IPV4的能力，套上WARP的ip，变成双栈VPS！

2：基本能隐藏VPS的真实IP！

3：WARP分配的IPV4或者IPV6的IP段，都支持奈非Netflix流媒体，无视VPS原IP限制！

4：加速VPS到CloudFlare CDN节点访问速度！

5：避开原VPS的IP需要谷歌验证码问题！

6：原IPV4下，WARP的IPV6替代HE tunnelbroker IPV6的隧道代理方案，做IPV6 VPS跳板机代理更加稳定！
```
</details>

<details>
<summary>给IPV4+IPV6双栈VPS添加WARP的好处</summary>
    
```bash
1：基本能隐藏VPS的真实IP！

2：WARP分配的IPV4或者IPV6的IP段，都支持奈非Netflix流媒体，无视VPS原IP限制！

3：加速VPS到CloudFlare CDN节点访问速度！

4：避开原VPS的IP需要谷歌验证码问题！
```
</details>

<details>
<summary>不稳定或者不足点</summary>
    
```bash
1：warp的IP与原生IP在Youtube上速度对比，并不一定有优势，具体看网络环境！
    
2：warp的IP归属国家一般与原生IP一致，但可能会自动改变！

3：由于warp是虚拟的IP，类似宝塔面板等相关工具可能需要另外的设置，请自行谷歌。
```
</details>

-------------------------------------------------------------------------------------------------------
### warp多功能一键脚本

- **脚本一：支持X86/ARM架构的纯IPV4 VPS与IPV4+IPV6双栈VPS**

```
wget -N --no-check-certificate https://raw.githubusercontent.com/you4728/Oracle-warp/main/multi.sh && chmod +x multi.sh && ./multi.sh
```

进入脚本快捷方式 ```bash ~/multi.sh```

---------------------------------------------------------------------------------------------------
- **脚本二：支持X86/ARM架构的纯IPV6 VPS**

- 如未执行上面的root一键脚本，先执行```sudo -i```进入root模式，后执行```echo -e nameserver 2a00:1098:2c::1 > /etc/resolv.conf```
```
wget -N --no-check-certificate https://raw.githubusercontent.com/YG-tsj/Pro-warp/main/multiOV6.sh && chmod +x multiOV6.sh && ./multiOV6.sh
```

纯IPV6建议后续只用快捷方式进入脚本 ```bash ~/multiOV6.sh```

----------------------------------------------------------------------------------------

### warp多功能一键脚本各功能简析

- **一、开启甲骨文VPS所有端口（甲骨文专用，务必选择）：**

解决代理协议申请证书发生Nginx等相关报错问题，完成后将自动断开VPS连接！

- **二、更新系统内核：**

因为5.6版本以上内核才集成Wireguard，内核集成方案在理论上网络效率最高！（网络性能：内核集成>内核模块>Wireguard-Go）

自动检测内核版本功能已集成于5-10脚本中，5.6以下内核将自动终止脚本运行并提示升级内核！

更新完成后将自动断开VPS连接！

- **三、开启原生BBR加速（秋水逸冰版）：**

按任意键即可安装成功，检测BBR是否生效(显示有BBR，说明成功)：lsmod | grep bbr

- **四、奈非Netflix检测(sjlleo版)：**

支持IPV4/IPV6检测，结果非常详细。

![4f396307256bfefd7c92d6f667fea45](https://user-images.githubusercontent.com/80431714/121798699-62b3b700-cc5a-11eb-81f0-49a0d2fcdaf7.png)


- **五、安装WARP脚本**

- **（仅支持 纯IPV4 VPS）**

脚本5、结果表现为2个IP：VPS本地IPV4+WARP虚拟IPV6

脚本6、结果表现为3个IP：VPS本地IPV4+WARP虚拟IPV4+WARP虚拟IPV6

脚本7、结果表现为2个IP：VPS本地IPV4+WARP虚拟IPV4

- **（仅支持IPV4+IPV6双栈VPS）**

脚本8、结果表现为3个IP：VPS本地IPV4+VPS本地IPV6+WARP虚拟IPV6

脚本9、结果表现为4个IP：VPS本地IPV4+VPS本地IPV6+WARP虚拟IPV6+WARP虚拟IPV4

脚本10、结果表现为3个IP：VPS本地IPV4+VPS本地IPV6+WARP虚拟IPV4

- **（仅支持 纯IPV6 VPS）**

脚本5、结果表现为3个IP：VPS本地IPV6+WARP虚拟IPV6+WARP虚拟IPV4

脚本6、结果表现为2个IP：VPS本地IPV6+WARP虚拟IPV4

目前（VPS本地IPV6+WARP虚拟IPV6，无IPV4）这种形式的应用应该不多吧，日后会加上。

- **六、永久关闭WARP功能：**

作用1：永久关闭WARP分配的虚拟IP，还原当前VPS的本地IP。

作用2：如之前已安装了一种WARP方案，现更换另一种WARP方案，请先关闭WARP功能，再执行安装WARP脚本。

- **七、启动并开机自启WARP功能：**

作用：永久关闭WARP功能后的再次启用。

因WARP脚本默认集成该功能，所以脚本安装成功后不必再执行该项。

- **八、查看当前VPS的IPV4/IPV6地址：**

顾名思义，当前正在运行的IP地址。

- **九、代理协议脚本选择**

支持IPV4/IPV6/X86/ARM的全面脚本 ，推荐！
mack-a脚本地址：https://github.com/mack-a/v2ray-agent

支持IPV4/IPV6/X86的脚本
phlinhng脚本地址：https://github.com/phlinhng/v2ray-tcp-tls-web

注意：域名解析所填写的IP必须是VPS本地IP，与WARP分配的IP没关系！

- **十、重启VPS实例（俗话说：重启解决99%的问题）**
 
甲骨文云也可以登录网页，进入实例后台，执行“重新引导”，在后台重启。

------------------------------------------------------------------------------------------------------
### 自定义ip分流配置模板说明

IPV4 VPS WARP专用分流配置文件(以下默认全局IPV4优先，IP、域名自定义教程，参考https://youtu.be/fY9HDLJ7mnM)
```
{ 
"outbounds": [
    {
      "tag":"IP4-out",
      "protocol": "freedom",
      "settings": {}
    },
    {
      "tag":"IP6-out",
      "protocol": "freedom",
      "settings": {
        "domainStrategy": "UseIPv6" 
      }
    }
  ],
  "routing": {
    "rules": [
      {
        "type": "field",
        "outboundTag": "IP4-out",
        "domain": [""] 
      },
      {
        "type": "field",
        "outboundTag": "IP6-out",
        "network": "udp,tcp" 
      }
    ]
  }
}
```
----------------------------------------------------------------------------------------------

### 相关附加说明

- 纯IPV6下登录SSH（确保本地支持IPV6，可参考德鸡EUserv相关教程）

- 提示：配置文件wgcf.conf和注册文件wgcf-account.toml都已备份在/etc/wireguard目录下！

- 查看WARP当前统计状态：wg

相关WARP进程命令
手动临时关闭WARP网络接口

wg-quick down wgcf
手动开启WARP网络接口

wg-quick up wgcf
启动systemctl enable wg-quick@wgcf

开始systemctl start wg-quick@wgcf

重启systemctl restart wg-quick@wgcf

停止systemctl stop wg-quick@wgcf

关闭systemctl disable wg-quick@wgcf

感谢P3terx大及原创者们，参考来源：

https://p3terx.com/archives/debian-linux-vps-server-wireguard-installation-tutorial.html

https://p3terx.com/archives/use-cloudflare-warp-to-add-extra-ipv4-or-ipv6-network-support-to-vps-servers-for-free.html

https://luotianyi.vc/5252.html

https://hiram.wang/cloudflare-wrap-vps/
