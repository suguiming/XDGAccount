# XD-Intl Account

## 前提条件

使用 XDGAccount 前提是必须使用以下依赖库:

* [XDGCommon](https://github.com/Roongflee/XDGCommon.git)

## 命名空间

```c#
using XD.Intl.Account
```

## 接口描述
###登录
```c#
 XDGAccount.Login(user=
{
    //返回用户信息
},(error)=>
{
    //登陆失败
});
```
###获取用户信息
```c#
 XDGAccount.GetUser((user)=
{
    //返回用户信息
},(error)=>
{
    //获取失败
});
```
###添加用户状态回调
```c#
 XDGAccount.AddUserStatusChangeCallback((code)=
{

});
```
###用户中心
```c#
  XDGAccount.OpenUserCenter();
```
###用户信息说明
```c#
public class XDGUser
{
[Serializable]
public long userId; //是long 不是 int !

// The user’s user ID in string.
public string sub;

// The user's user name.
public string name;

// The user's current loginType.
public string loginType; //App传来的是字符串，如 TapTap。 通过 GetLoginType() 方法获取枚举

public List<string> boundAccounts;

// The user's token.
public XDGAccessToken token;

[Serializable]

   public class XDGAccessToken{
    // 唯一标志
    public string kid;

    // 认证码类型
    public string tokenType;

    // mac密钥
    public string macKey;

    // mac密钥计算方式
    public string macAlgorithm;
        
    }
}
```


...