## Objection 简介
    objection - runtime mobile exploration
    Objection是一款移动设备运行时漏洞利用工具,该工具由Frida驱动,可以帮助研究人员访问移动端应用程序。

### Usage：
    
    1. 启动：
    
        objection -g cn.com.sina.finance explore

    2. 查看环境
    
        env

    3. 重点
    
        3.1 列举so文件
            memory list modules
            
        3.2 列举so文件导出方法
        
            memory list exports libA3AEECD8.so
            
        3.3 将结果写入文件中
        
            memory list exports libA3AEECD8.so --json /root/test.json
    
        3.4 查找可以hook的类
        
            android hooking list classes
            
        3.5 查找带关键词的类
        
            android hooking search classes display
            
        3.6 查看对应类有哪些方法
        
            android hooking list class_methods com.android.settings.DisplaySettings
        
        3.7 生产hook类的代码
        
            android hooking generate simple d.d.a.g.c
            
        3.8 hook类的所以方法
        
            android hooking watch class d.d.a.g.c
            android hooking watch class_method okhttp3.HttpUrl$Builder$ParseResult --dump-args --dump-return
        
        3.9 帮助类
        
            help android hooking watch class
            
        4.0 禁用sslpinning
        
            android sslpinning disable
            
        4.1 搜索类的实列
        
            android heap search instances com.example.httptest.MainActivity
            android heap execute 0x1fc6 getMethod
            
        4.2 搜索activties
        
            android hooking list activities
            android intent launch_activity com.example.httptest.MainActivity
        
        4.3 搜索类中的方法
            android hooking search classes com.example.httptest.MainActivity
            android hooking list class_methods com.example.httptest.MainActivity$1
            android hooking list class_methods com.example.httptest.MainActivity$ChangeOrientation
        
        4.4 内存搜索/修改
            memory search "64 65 78 0a 30 33 35 00"
            memory search "99999999999" --string
            memory write 0x130b4060 "99999999999" --string
        
### Objection源码：
    
    https://github.com/sensepost/objection.git


