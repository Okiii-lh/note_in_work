<center>MMC在一个管理单元中检测到错误，将卸载此管理单元</center>

直接点击下一步

会跳出报错信息

错误提示中包含“FX:{c7b8fb07-bfe1-4c2e-9217-7a69a95bbac4}

win+R键，输入regedit，在“\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MMC\SnapIns”下找到

FX:{b05566ad-fe9c-4363-be05-7a4cbb7cb510}

（可能还有其他项，只要是AssemblyName对应的数据为TaskScheduler的都删了）

到C:\Windows\System32里找到taskschd.msc运行即可打开任务计划程序。

