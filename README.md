# 有帮助记得先Star，感谢!!!
- [此处存放个人编写的常用shell脚本，其中可能使用到其他项目源码，若侵权联系删除](#此处存放个人编写的常用shell脚本，其中可能使用到其他项目源码，若侵权联系删除)
    * [一、一键修改Ubuntu系统root密码](#一、一键修改Ubuntu系统root密码)
        + [1.一键脚本](#1.一键脚本)
        + [2.功能](#2.功能)
        + [3.示例图](#3.示例图)
    * [二、一键初始化常用系统设置](#二、一键初始化常用系统设置)
        + [1.一键脚本](#1.一键脚本)
        + [2.功能](#2.功能)
        + [3.示例图](#3.示例图)
    * [三、acme证书申请一键脚本](#三、acme证书申请一键脚本)
        + [1.用到的官仓：](#1.用到的官仓：)
        + [2.功能](#2.功能)
        + [3.一键脚本](#3.一键脚本)
        + [4.示例图](#4.示例图)
    * [四、docker容器中的mysql备份/还原脚本](#四、docker容器中的mysql备份/还原脚本)
        + [1.用到的官仓](#1.用到的官仓)
        + [2.功能](#2.功能)
        + [3.使用](#3.使用)
        + [4.示例图](#4.示例图)
    * [五、aliyunpan备份脚本(建议aliyunpan在root目录下)](#五、aliyunpan备份脚本(建议aliyunpan在root目录下))
        + [1.用到的官仓](#1.用到的官仓)
        + [2.功能](#2.功能)
        + [3.使用](#3.使用)
        + [4.示例图](#4.示例图)
    * [六、aliyunpan恢复脚本(建议aliyunpan在root目录下)](#六、aliyunpan恢复脚本(建议aliyunpan在root目录下))
        + [1.用到的官仓](#1.用到的官仓)
        + [2.功能](#2.功能)
        + [3.使用](#3.使用)
        + [4.示例图](#4.示例图)
---

# 此处存放个人编写的常用shell脚本，其中可能使用到其他项目源码，若侵权联系删除
## 一、一键修改Ubuntu系统root密码
目前测试系统：`arm/amd Ubuntu`
### 1.一键脚本
+ ```bash <(curl -Ls https://github.com/baoqihui/script/raw/main/root.sh)```
### 2.功能
1. 修改Ubuntu的root密码
2. 持久化root密码，可永久连接
### 3.示例图
1. 信息定制
  + ![image](https://user-images.githubusercontent.com/50536515/155873326-0c5c43a5-ad59-44fb-b9b0-665b30aeaedb.png)
2. 结果生成
  + ![image](https://user-images.githubusercontent.com/50536515/155873404-161f3f3b-31bd-4db9-ad1d-175fd8493a28.png)
  + ![image](https://user-images.githubusercontent.com/50536515/155873415-fac78fce-3a6e-4772-9012-8b8729ec4b55.png)
---

## 二、一键初始化常用系统设置
目前测试系统：`arm/amd Ubuntu`
### 1.一键脚本
+ ```bash <(curl -Ls https://github.com/baoqihui/script/raw/main/init.sh)```
### 2.功能
1. 开放所有端口
2. 统一本地时间
3. 更新及安装组件
4. 关闭Iptable规则
5. 开启BBR加速
6. 测速
### 3.示例图
1. 信息定制
  + ![image](https://user-images.githubusercontent.com/50536515/155878543-1592d57b-2d56-461f-b3af-bc185f1a43f3.png)

2. 结果生成
  + ![image](https://user-images.githubusercontent.com/50536515/155878570-152590ec-2c7a-4ddb-9464-8a69a2ab0441.png)
  + ![image](https://user-images.githubusercontent.com/50536515/155878606-05a93768-9977-4777-9838-dacdb04e264d.png)

---

## 三、acme证书申请一键脚本
目前测试系统：`arm/amd Ubuntu`
### 1.用到的官仓：
+ Acme官方: https://github.com/acmesh-official/acme.sh 
### 2.功能
1. 全自动安装证书到指定文件夹
2. 批量安装
3. 自动续期
4. docker中nginx续费重启
### 3.一键脚本
+ ```bash <(curl -Ls https://github.com/baoqihui/script/raw/main/cert.sh)```
### 4.示例图
1. 信息定制
  + ![image](https://user-images.githubusercontent.com/50536515/154844456-c7b49470-323d-421b-8c8b-73f8ed29b1bb.png)
2. 结果生成
  + ![image](https://user-images.githubusercontent.com/50536515/154844580-602b13c4-255f-4b64-96ad-8f1601fd8fe4.png)

---
## 四、docker容器中的mysql备份/还原脚本
### 1.用到的官仓
+ docker
+ mysql
### 2.功能
+ 备份/还原docker容器中的mysql数据库
+ 搭配上定时任务可以自动备份,例如每两小时备份： `echo "0 */2 * * * bash /root/backup-mysql.sh > /out/backup-mysql.log 2&1 &" >>/var/spool/cron/crontabs/root`
### 3.使用
1. 下载脚本并配置：`wget -O /root/backup-mysql.sh https://raw.githubusercontent.com/baoqihui/script/main/backup-mysql.sh`
2. 还原：`bash <(curl -Ls https://raw.githubusercontent.com/baoqihui/script/main/reciver-mysql.sh)`
### 4.示例图
![image](https://user-images.githubusercontent.com/50536515/162558815-0a5f5868-9c17-4d14-a65e-0cca0e519c58.png)

---
## 五、aliyunpan备份脚本(建议aliyunpan在root目录下)
### 1.用到的官仓
+ aliyunpan：https://github.com/tickstep/aliyunpan
+ zip
### 2.功能
+ 一键压缩打包并上传到到阿里云盘
+ 搭配上定时任务可以自动备份,例如每天0点备份： `echo "0 0 * * * bash /root/backup-ali.sh > /out/backup-ali.log 2&1 &" >>/var/spool/cron/crontabs/root`
### 3.使用
1. 由于zip工具可能不自带，先下载：`apt install zip`
2. 自行去下载配置aliyunpan到root目录：https://github.com/tickstep/aliyunpan
3. 下载脚本并配置：`wget -O /root/backup-ali.sh https://raw.githubusercontent.com/baoqihui/script/main/backup-ali.sh`
### 4.示例图
![image](https://user-images.githubusercontent.com/50536515/162558220-fbf1afc4-68b2-4b56-85c5-5d7205b4e68a.png)

---
## 六、aliyunpan恢复脚本(建议aliyunpan在root目录下)
### 1.用到的官仓
+ aliyunpan：https://github.com/tickstep/aliyunpan
+ zip
### 2.功能
+ 一键恢复并解压到原始目录
### 3.使用
1. 由于zip工具可能不自带，先下载：`apt install zip`
2. 自行去下载配置aliyunpan到root目录：https://github.com/tickstep/aliyunpan
3. 一键脚本：`bash <(curl -Ls https://raw.githubusercontent.com/baoqihui/script/main/recover-ali.sh)`
### 4.示例图
+ ![image](https://user-images.githubusercontent.com/50536515/162557393-4fb3eb6a-704c-4d10-b95c-5322efccc84f.png)

