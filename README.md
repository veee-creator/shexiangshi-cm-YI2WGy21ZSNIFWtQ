[合集 \- OpenTools(9\)](https://github.com)[1\..NET使用P/Invoke来实现注册表的增、删、改、查功能05\-14](https://github.com/weskynet/p/18191869)[2\..NET实现获取NTP服务器时间并同步(附带Windows系统启用NTP服务功能)05\-15](https://github.com/weskynet/p/18194418)[3\.工业福利！用.NET快速开发物联网扫码器设备的通用扫码功能05\-17](https://github.com/weskynet/p/18198774)[4\.上位机开发福利！快速掌握.NET中的Modbus通信05\-22](https://github.com/weskynet/p/18206594):[西部世界官网](https://tianchuang88.com)[5\.使用Wesky.Net.Opentools库,一行代码实现实体类类型转换为Json格式字符串06\-05](https://github.com/weskynet/p/18233902)[6\.使用Wesky.Net.Opentools库，一行代码实现自动解析实体类summary注释信息（可用于数据实体文档的快速实现）06\-06](https://github.com/weskynet/p/18236082)[7\.谁说.net core不好动态访问webservice？看这篇文章，C\#快速实现动态访问webservice，兼容.net framework和.net core\+06\-10](https://github.com/weskynet/p/18241230)[8\.使用Wesky.Net.OpenTools包来快速实现嵌套型结构体数据转换功能06\-12](https://github.com/weskynet/p/18244720)9\.基于DPAPI\+RDP技术实现本地打开远程程序，并映射到本地机器桌面上10\-03收起
 
本教程使用工具所使用的环境说明：
启动器开发工具：VS2022
启动器所用客户端技术：.NET 8 \+ WPF
启动器其他技术：DPAPI
启动器发布的可执行程序，系统要求：Windows 7以及以上，X64
如果需要本程序，可以在网盘获取。网盘地址：
通过网盘分享的文件：RemoteShadowApp.7z 链接: https://pan.baidu.com/s/1QPstE5\-1zPK\-qOp8GQ90ew?pwd\=6666 提取码: 6666
 
接下来是该工具的具体使用教程。
先对远程服务器上面的注册表进行设置。路径如下：HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services
如下图所示，目前里面没啥东西。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122751913-1908853221.png)
 
可以通过当前工具进行设置，在服务器上面打开RemoteShadowApp程序，然后点击设置注册表，即可看到注册表被自动创建成功了。这样可以直接快速设置注册表。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752157-224786781.png)
当然，如果不想在服务器上面运行，也可以手动自己设置一下。自己创建一个注册表，创建DWORD键值对，名称是 fAllowUnlistedRemotePrograms 对应的值设为1。如果觉得麻烦，那就用我上面的工具直接设置，效果也是一样的。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122751939-1501137873.png)
 
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752134-2090311721.png)
 
在本机机器上面，就可以通过远程访问目标服务器的程序了。操作如下：
例如我要打开远程桌面上的Notepad\+\+程序
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752033-77110227.png)
我需要获取服务器的IP、登陆的用户名、密码、以及NotePad\+\+的启动程序的绝对路径，例如如下图所示。我没做记住信息功能，所以大家也可以自己创建一个记事本之类的，存储你的远程程序信息，方便粘贴进去填写。都输入完毕以后，点击 【打开远程程序】 按钮
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122751882-2025488218.png)
 
注意事项：如果远程服务器有360等软件，可能会限制你的权限，例如一直卡在这个界面
 
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752110-1580128594.png)
此刻你需要点开 显示详细信息，可以看到有一个登陆按钮，点击登陆即可。这个只有部分远程服务器会出现，如果本机没有一些限制设置或者安全软件，这一步不会出现。仅在有出现这个现象的时候才需要这样操作。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752182-610255401.png)
打开的远程的notepad\+\+程序，效果如图所示。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122751969-941561838.png)
接着我们打开远程服务器，看下现象。具体如图所示效果。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752385-904242684.png)
 
支持打开多个远程程序，例如，我现在打开一个以前自己写的控制台程序服务，地址如下
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752138-1345035759.png)
在刚才的程序里面，更改启动的路径为上面的控制台服务路径，然后启动。可以看到启动成功了。并且和上一个notepad程序可以共存。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752156-190594673.png)
同样，服务器上面也并不存在控制台程序的页面，但是存在进程。控制台程序也是占用服务器资源，而不会占用本地资源。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752244-1615215465.png)
如果当前没啥需要，就可以退出启动器，退出启动器对已经打开的远程程序没有任何影响。启动器只是用来提供远程程序作用，没有其他功能。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122752108-464577188.png)
 
启动器核心功能，主要是DPAPI加密功能。DPAPI（数据保护应用程序编程接口）是微软提供的一个用于帮助保护数据安全的API，它可以简化在Windows平台上的数据加密过程。DPAPI 提供了一个系统级别的加密服务，其特点是不需要应用程序自行处理加密密钥的存储和保护。DPAPI主要用于保护敏感信息，如密码、密钥和其他个人或系统数据。
如下所示代码，我在Wesky.Net.Opentools开源项目上也有集成该功能。此处我在本程序内直接使用来加密。必须加密以后的密码，才能被远程服务器识别。
![0](https://img2024.cnblogs.com/blog/1995789/202410/1995789-20241003122751813-540646592.png)
 
下面是DPAPI具体的加密和解密过程：



```
 /// 
 /// 加密数据
 /// 
 /// 
 /// 
 public static string EncryptData(string dataToEncrypt)
 {
     try
     {
         byte[] secret = Encoding.Unicode.GetBytes(dataToEncrypt);
         byte[] encryptedSecret = ProtectedData.Protect(secret, additionalEntropy, DataProtectionScope.LocalMachine);
         string res = string.Empty;
         foreach (byte b in encryptedSecret)
         {
             res += b.ToString("X2");
         }
         return res;

     }
     catch (Exception ex)
     {
         Console.WriteLine("加密过程中出现异常: " + ex.Message);
         return null;
     }
 }

 /// 
 /// 解密数据
 /// 
 /// 
 /// 
 public static string DecryptData(string hexEncryptedData)
 {
     try
     {
         byte[] dataToDecrypt = ConvertHexStringToByteArray(hexEncryptedData);
         byte[] decryptedData = ProtectedData.Unprotect(dataToDecrypt, null, DataProtectionScope.LocalMachine);
         return Encoding.Default.GetString(decryptedData);
     }
     catch (Exception ex)
     {
         Console.WriteLine("解密过程中出现异常: " + ex.Message);
         return null;
     }
 }
```


 



设置注册表的地方，也是很简单的一个写死的代码，供参考



```
 // 指定注册表键的路径
 string registryPath = @"SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services"; // 根据需要修改路径
 string valueName = "fAllowUnlistedRemotePrograms"; // 注册表项名称

 try
 {
     // 创建或打开指定的注册表键
     using (RegistryKey key = Registry.LocalMachine.CreateSubKey(registryPath))
     {
         if (key != null)
         {
             // 设置值为 DWORD32 类型，并赋值为 1
             key.SetValue(valueName, 1, RegistryValueKind.DWord);
             MessageBox.Show("注册表键已创建并赋值成功。");
         }
         else
         {
             MessageBox.Show("无法创建注册表。");
         }
     }
 }
 catch (UnauthorizedAccessException)
 {
     MessageBox.Show("您没有权限设置注册表，请以管理员身份运行程序。");
 }
 catch (Exception ex)
 {
     MessageBox.Show($"设置注册表发生错误: {ex.Message}");
 }
```


后记：本工具打开的远程程序，支持局域网、外网，只要你可以通过远程桌面访问的服务器或者电脑，都可以通过该方式进行启动。


如果以上内容对你有帮助，欢迎点赞、在看、转发和留言。感谢大家的支持。也欢迎关注公众号：【Dotnet Dancer】


 



 
 
