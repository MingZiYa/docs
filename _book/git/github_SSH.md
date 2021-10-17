
## 创建github SSH密钥
   *  ssh-keygen -t ed25519 -C "mingziya911@gmail.com" 更换为自己的邮箱
   *  ，
   *  `Enter file in which to save the key (/c/Users/hp/.ssh/id_ed25519):`
   	直接按Enter使用默认的密钥名称
	   *  Generating public/private ed25519 key pair.
		Enter file in which to save the key (/c/Users/hp/.ssh/id_ed25519): 提示输入密钥的名称
		Enter passphrase (empty for no passphrase): 输入密码（注意不是Github的密码）
		Enter same passphrase again: 再次输入密码

		直接Enter使用默认的密钥
		不设置密码，使用SSH私钥连接

	创建完成提示如下消息
	***
		Your identification has been saved in /c/Users/hp/.ssh/id_ed25519
		Your public key has been saved in */c/Users/hp/.ssh/id_ed25519.pub* 密钥地址
		The key fingerprint is:
		SHA256:QpTowBBZ3Xk7Rebr/NKQPO0BNf+5xTg24MsrAurOAWA mingziya911@gmail.com
		The key's randomart image is:
		+--[ED25519 256]--+
		|o*.. o.o .o      |
		|. o o.+ .o. o    |
		|.E o  .. o.. o   |
		|..  ..  o ... .  |
		|  .   . So.= . +.|
		|   .  .. o= + =.+|
		|    .. .  o* + oo|
		|   ...  . o.=  . |
		|   o+    . oo.   |
		+----[SHA256]-----+

	***

	进入/c/Users/hp/.ssh/id_ed25519.pub复制 id_ed25519.pub文件

	在github账号中填写公钥
		1. 进入github设置
		2. 选择SSH and GPG keys
		3. New SSH key
			* Title 输入git(用于标记,不指定名称)

			* key 把新生成的SSH密钥复制到这里
			  `ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOyQCLJ2ozpa7iLvSN8SDBU3JkI+MBCo/XM6jjOm+HDB mingziya911@gmail.com`

			 * 点击*Add SSH key* 完成添加
			 * 这里提示要输入密码，输入密码完成

1. 将您的硬件安全密钥插入您的计算机。

2. 打开Git Bash。

3. 粘贴下面的文本，替换为您在GitHub上的帐户的电子邮件地址。

	```
	$ ssh-keygen -t ed25519-sk -C "your_email@example.com"
	```

	<table>
		<tr style="border-radius: 30px;">
			<td style="border: 1px solid #76C773;">
				注意：如果命令失败并且您收到错误，invalid format或者feature not supported,您可能使用了不支持 Ed25519 算法的硬件安全密钥。改为输入以下命令。
				<br/><br/>
				$ ssh-keygen -t ecdsa-sk -C "your_email@example.com"<br/>
			</td>
		</tr>
	</table>
	
4. 出现提示时，触摸硬件安全密钥上的按钮。

5. 当系统提示您“输入要保存密钥的文件”时，按 Enter 接受默认文件位置。

	```
	> Enter a file in which to save the key (/c/Users/you/.ssh/id_ed25519_sk):[Press enter]
	```

6. 当系统提示您输入密码时，请按Enter。
	
	```
	> Enter passphrase (empty for no passphrase): [Type a passphrase]
	> Enter same passphrase again: [Type passphrase again]
	```
	
7. 将 SSH 密钥添加到您在 GitHub 上的帐户。有关更多信息，请参阅“向您的 GitHub 帐户添加新的 SSH 密钥”。

