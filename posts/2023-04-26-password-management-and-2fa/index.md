# 密码管理和2FA管理软件


<!--more-->
## 密码管理

现在网络上各种网站服务非常多，每个人至少都有注册过几十上百个网站，账号密码的管理显得尤为重要，很多人为了便于记忆，多种账号采用相同的密码，这种做法非常不安全，因为一旦有一个平台的密码泄露，就很容易被撞库攻击。
> 撞库是黑客通过收集互联网已泄露的用户和密码信息，生成对应的字典表，尝试批量登录其他网站后，得到一系列可以登录的用户。很多用户在不同网站使用的是相同的帐号密码，因此黑客可以通过获取用户在A网站的账户从而尝试登录B网址，这就可以理解为撞库攻击。

另一个普遍的现象就是设置过于简单的密码，比如123456等这些非常常见的简单密码，非常容易被暴力破解。每年都有一些机构公布最常用的密码列表，这些密码要避开。

密码管理工具 NordPass公布了 2022 年最常用密码列表，2022 年最常用密码相比过去几年差异并不大，排在榜首的是 password，有近 500 万人使用。其次分别为：123456、123456789、guest、qwerty、12345678、111111、12345、col123456 和 123123。


### 密码设置：

密码设置要注意以下要点：

1. 设置强密码  
密码设置要满足一定复杂性，最好是10位及以上，包含大小写字母+数字+符号，避开常用短语、键盘顺序键位、生日信息等。

2. 不要使用重复密码  
每个网站的密码都做区分，不要设置相同的密码。多个账户的单一密码如果有一个遭到入侵，所有的其他账户都将受到威胁。

3. 检查密码强度并定期更新  
定期评估密码健康情况，定期更新，像很多密码管理器或浏览器保持的密码都会提示此密码被使用的情况。

4. 开启多重验证  
重要账户开启多重验证，也就是除了密码校验后，还要再进行另外一重认证。主流的方式有：
	- 验证另一个账户所有权：邮件，短信，微信等
	- 验证生物特征：人脸，指纹，声纹等
	- 验证动态令牌：TOTP动态口令等
	- 验证硬件所有权：U盾等

### 密码分级： 

密码设置时，建议按账户重要性进行分级管理，比如涉及支付类的，为最高等级，要重点管理，密码设置和使用要加强验证。社交类软件，为一个等级，普通日常网站的为一个等级，不同级别的密码千万不要雷同。


### 密码记忆：  

密码记忆是一个重要的问题，很多人就是记不住才设置雷同的密码。那么这里有个设置密码的策略，可以比较方便的记忆密码。

设置密码时采用一套公式作为设置原则，跟对应产品名称关联挂钩。

举例：

8位固定字符+产品名最后一个字的声调+第一个字笔画+开发者第一个字的拼音并且第二个字母大写

以qq为例，8位固定字符!!6&3@1#（自己记忆好）+1（Q第一声）+2（Q笔画2）+tEng   
那么密码就是：!!6&3@1#12tEng   

这样，你就可以给每个网站设置唯一的密码，并且密码也足够复杂，而且还方便记忆，你只要记住了你的公式即可。建议多备几个公式，不同等级的用不同的公式。

### 密码存放：  

密码除了靠记忆，还是有必要记录下来的，否则忘记了就麻烦了。但是怎么放，是保证密码安全的重要因素。

**原则**：一个存放的重要原则，决不能明文保存，自己还要再用自己一套加密规则再加密一下。

写在纸上是不可取的做法，这是一些人会犯的低级错误。你的纸被人拿到你所有密码都泄露了。

**存放方法：**  
1. 文档记录，word，excel用非明文登记，整个文档再加密保存，word。
2. 手机自带备忘录保存，用大厂手机如苹果华为小米等自带的备忘录非明文登记，备忘录记得再加密。
3. 密码管理软件，市面上有很多比较知名的密码管理软件，专门帮你保存所有账户密码，支持全平台，也有开源可以自己自建服务端。

最安全的是文档加密记录后离线备份，相当于你存在U盘里，然后拔掉存放起来。

如果要上传云笔记云空间切记一定要先登记在文档上加密后再上传，不要直接使用云笔记记录。国内厂家云笔记云服务厂家要慎重，除了阿里，腾讯这几个大厂，小厂的不能信，关停和信息泄露是常有的事。

## 密码管理软件

密码管理软件可能有些人比较陌生，这是专门管理密码和存放的

## 2FA双因素认证

## 安全备份策略


---

> 作者: Kingpo  
> URL: https://ttzz.eu.org/posts/2023-04-26-password-management-and-2fa/  
