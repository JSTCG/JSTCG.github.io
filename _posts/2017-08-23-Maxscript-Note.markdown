---
layout: post
title: Maxscript Note
date: 2017-08-23 11:12:28.000000000 +08:00
tags: MXS
---
**MXS备忘**
- **样条线** ：
>获取样条线信息
```swift
numsplines $
numknots $
FP=(getKnotPoint $ 1 1)
EP=(getKnotPoint $ 1 (numknots $))
```
- **多线程** ：
>MaxScript里开不了线程，但是可以用BackgroundWorker来做后台处理
```swift
Fn BackgroundTcpListenerDoWork theSender theEvent =
(
    IPAddress = DotNetClass "System.Net.IPAddress"
    theIPAddress = IPAddress.Parse "127.0.0.1"
    theTcpListener = DotNetObject "System.Net.Sockets.TcpListener" theIPAddress 7457
    theTcpListener.Start()
    while not theSender.CancellationPending do
    (
        theSocket = theTcpListener.AcceptSocket()
        theByteStream = DotNetObject "System.Byte[]" 8192
        theSocket.Receive theByteStream
        Encoding = DotnetClass  "System.Text.Encoding"
        theString = Encoding.UTF8.GetString(theByteStream)
        if not theSender.CancellationPending do Execute theString
    )
    theTcpListener.Stop()
)
BackgroundWorker = DotNetObject "System.ComponentModel.BackgroundWorker"
DotNet.AddEventHandler BackgroundWorker "DoWork" BackgroundTcpListenerDoWork
BackgroundWorker.WorkerSupportsCancellation = true
BackgroundWorker.RunWorkerAsync()
```
- **2011处理Atsops时のBug** ：
>需要关闭资源追踪ATSOps.Silent=false
```swift
--ATSOps.Silent=false
atsops.selectfiles "C:\Users\Administrator\Desktop\++.jpg"
atsops.retargetselection "C:\Users\Administrator\Desktop\1\++.jpg"
atsops.refresh()
Atsops.Visible = true
```
