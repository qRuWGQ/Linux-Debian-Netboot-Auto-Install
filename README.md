# Linux-Debian-Netboot-Auto-Install

一键网络重装 Debian 12 纯净系统  

脚本开源透明，安装包均来自官方，可放心食用

脚本运行要求:
> 系统: `Debian/Ubuntu` ｜ `Centos/Redhat`  
> 架构: `amd64` | `arm64` | `i386`

功能一览:  
• 自动识别引导方式和分区表类型  
• APT镜像源选择，系统镜像也是从选择的源下载  
• 自动识别默认网口或手动指定，自动识别网络类型是DHCP或static  
• ROOT密码设定
• 默认使用的是当前系统所在的磁盘进行自动分区，后续会支持手动指定要使用的硬盘  
• 目前安装的系统是 `Debian 12`，后续会支持其他版本的系统

目前测试过的平台:  

| 平台        | 引导方式 | 分区表类型 | 说明                                            |
|-----------|------|-------|-----------------------------------------------|
| Dogyun    | BIOS | MBR   | 支持                                            |
| 阿里云ECS服务器 | BIOS | MBR   | 部分情况支持，使用脚本前，通过ecs面板将系统安装为Debian 10，不然脚本执行不成功 |
| 阿里云轻量云服务器 | BIOS | MBR   | 支持                                            |
| 阿里云轻量云服务器 | BIOS | GPT   | 支持                                            |
| Vultr     | UEFI | GPT   | 支持                                            |
| LocVPS    | BIOS | MBR   | 支持                                            |
| DMIT      | BIOS | MBR   | 支持                                            |

~~正常情况一般都支持，除非你的分区表类型比较阴间，使用的是：`Hybrid MBR 混合分区表`, 那本脚本暂时不支持，目前已知不支持的平台：`HostKvm`~~  
问题已得到解决，现在支持使用bios引导+GPT分区的系统了  

某些环境不一定能完全自动安装成功，如果长时间未能登录SSH，自行前往VNC控制台进行查看或操作  

## 执行

```shell
curl https://raw.githubusercontent.com/qRuWGQ/Linux-Debian-Netboot-Auto-Install/main/install.sh | bash
```
