# 信息安全

PRemoteM 设计的初衷在于希望用户能随时随地快速地开启新的远程会话，于是我们很难平衡便利性与安全性。考虑到 PRemoteM 的使用群体应当是对计算机安全有一定认知的业内人士，于是我们决定更多关注于**便利性**，而将安全性交给系统、安全软件、良好的用户习惯来保护。因此 PRemoteM 将只提供最基本的信息安全保障，不提供类似于启动密码之类的功能。

## 为何没有做开机密码？

由于本程序是一个常驻后台，通过启动器（Alt + M）启动会话的远程管理工具，如果每次开启启动器都要输入密码，那么使用体验将大打折扣。而如果仅在程序启动时要求密码，那么安全性其实并未能够得到妥善保障。考虑到这些，我们认为安全性由系统、安全软件、良好的用户习惯保障才是长远之计。只要用户意识到在自己离开计算机时应当锁定系统，那么 PRemoteM 就不必为自己再加一层枷锁。而若用户没有这样的安全意识，那么就算 PRemoteM 加入了启动密码，信息仍有可能从其他方式被泄露。

## 我们提供的加密功能

于是我们只提供了数据库的的 RSA 加密功能（账号、密码等），同时推荐开启硬盘加密(like [Bitlocker](https://docs.microsoft.com/en-us/windows/security/information-protection/)etc.) 。以确保 PRemoteM 数据库被泄露，或计算机硬盘遭到物理破解时，盗窃者依旧无法获取到其中的机密。

### 注意
**RSA 加密功能默认关闭，你需要在设置中手动创建自己的 RSA 密钥，开启加密功能。**

一个较为推荐的做法是把数据库和密钥防在随身的加密U盘中，每次开启软件前先插入该U盘。

## 总结

- 确保每次离开电脑后，系统都会被锁。
- (**推荐**) 开启 BitLocker in Windows 10。
- (**推荐**) 使用 RSA 加密保护你的数据。
- 同时要妥善保管你的 RSA 解密密钥。

## 附录：如何开启RSA加密

设置方法：

1. 在 <kbd>设置</kbd> → <kbd>数据与安全</kbd> 界面
2. 点击 <kbd>生成加密</kbd> 按钮后，你的数据将被加密，请将生成的**私钥**妥善保管.

<p align="center">
    <img src="https://github.com/VShawn/PRemoteM/raw/Doc/DocPic/Encryption.jpg" width="300"/>
</p>