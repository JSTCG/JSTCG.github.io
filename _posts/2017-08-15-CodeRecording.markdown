---
layout: post
title: CodeRecording
date: 2017-08-15 13:17:25.000000000 +08:00
tags: Coding
---
**Get**
- **重命名文件 ：** ：
>利用Move达到重命名
```swift
File.Move(@"C:\Users\Administrator\Desktop\Remote\Dmxs\AAA.jpg", @"C:\Users\Administrator\Desktop\Remote\Dmxs\BBB.jpg");
Directory.Move((Environment.GetFolderPath(Environment.SpecialFolder.ApplicationData) + @"\XXX"), @"C:\Users\Administrator\Desktop\");
```
- **获取文件夹文件数量** ：
>GetFileNumb(@"F:\Allen\Sun\Com");
```swift
private int GetFileNumb(string path)
{
    int Numb = 0;
    try
    {
        string[] directories = new string[0];
        directories = Directory.GetDirectories(path);
        foreach (string str2 in directories)
        {
            Numb += (new DirectoryInfo(str2)).GetFiles().Length;
        }
    }
    catch (Exception exception)
    {
        MessageBox.Show(exception.Message + " " + path);
    }
    return Numb;
}
```
- **根据域名或者计算机名获取IP**
>IP4与IP6
```swift
Dns.GetHostEntry("SUN").AddressList[0].ToString();
Dns.GetHostEntry("lisun.win").AddressList[0].ToString();
Dns.Resolve("SUN").AddressList[0].ToString();
Dns.Resolve("lisun.win").AddressList[0].ToString();
```
- **关键路径**
>C:\Users\Administrator\AppData\Roaming
```swift
System.Environment.GetFolderPath(Environment.SpecialFolder.ApplicationData);
```
- **7z压缩解压(需要SevenZip库)**
>7z压缩文件与解压
```swift
//压缩
SevenZip.SevenZipCompressor.SetLibraryPath(@"C:\Program Files\7-Zip\7z.dll");
var compressor = new SevenZipCompressor();
compressor.CompressionLevel = CompressionLevel.Ultra;//极限压缩
compressor.DirectoryStructure = true;// 是否保持目录结构，默认为true。
compressor.IncludeEmptyDirectories = true;// 是否包含空目录，默认true。
compressor.ZipEncryptionMethod = ZipEncryptionMethod.ZipCrypto;// 文件加密算法
compressor.FastCompression = false;// 尽快压缩（不会触发*Started事件，仅触发*Finished事件)
compressor.CompressDirectory(@"C:\Users\Administrator\Desktop\Test", @"C:\Users\Administrator\Desktop\Test.7z", true, "1234567");
//解压
SevenZipCompressor.SetLibraryPath(@"C:\Program Files\Sunlery\7z\7z.dll");
var Extractor_Dmxs = new SevenZipExtractor(Path.GetTempPath()+"Test.7z", "1234567");
```

- **委托**
>委托完成后并回调
```swift
private void DelegateWork()
{
  bool urlOK = false;
  try
  {
      HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://192.168.131.181/");
      HttpWebResponse resp = (HttpWebResponse)req.GetResponse();
      if (resp.StatusCode == HttpStatusCode.OK)
      {
          resp.Close();
          urlOK = true;
      }
  }
  catch (WebException webex)
  {
      urlOK = false;
      MessageBox.Show(webex.Message);
  }
}
private void CompleteMessage1(int AA,IAsyncResult iasyncResult_0)
{
    MessageBox.Show(this, "委托完成", "SunTools");
}
Action ACT = delegate() { DelegateWork(); };
ACT.BeginInvoke(new AsyncCallback(this.CompleteMessage), null);
```
- **flowLayoutPanel**
>取消水平滚动条的解决方法 Set AutoScroll to true Set WrapContents to false. Make sure the size is wider than the controls’ width plus the width of a vertical scrollbar.
```swift
FlowLayoutPanel1.AutoScroll = true;
FlowLayoutPanel1.WrapContents = false;
FlowLayoutPanel1.width = FlowLayoutPanel1.width+垂直条宽;
```
