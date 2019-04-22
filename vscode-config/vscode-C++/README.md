https://www.zhihu.com/question/30315894/answer/154979413
# C++环境
* LLVM Download Page 在此页面下载Clang。选Pre-Built Binaries中的Clang for Windows (64-bit)，不需要下.sig文件
* MinGW-w64 - for 32 and 64 bit Windows 在此页面下载MinGW-w64，点那个Download就行
* other:
>* 下载好了以后安装。添加环境变量时：选Add LLVM to the system PATH for all users（即第二项，不过第三项也差不多）。Clang的安装路径（Destination folder）我推荐填C:\LLVM，不装那里也行，下面的配置里路径就自己改。安装完了以后可能会弹出cmd说MSVC integration install failed。这个是因为Clang默认使用的是msvc的工具链，而我们选择的工具链是MinGW，所以就不用管这个提示。如果你想用别的工具链，参考第九点。
>* MinGW随便装哪，Architecture选x86_64，装好以后把东西全部复制到Clang的文件夹里去，他们会无冲突合并，效果图见下。同样，不做这一步也行，下面的配置里路径就自己改，还要手动把MinGW的bin文件夹加到path中，因为MinGW不会自己加。至于为什么既要装Clang又要装MinGW，是因为Clang没有头文件。然后就可以把MinGW删了（Uninstall.exe）。不建议安装多个MinGW，如果你安装了其他IDE需要注意把其他的MinGW从环境变量中去掉；也可以自己把他们的编译器设为Clang。因为几乎所有的轻量级IDE用的都是MinGW或TDM-GCC，它们不制造编译器，只是打包了一个。而且它们用在VSC里也会有奇怪的错误
# 需要安装的扩展：
* C/C++（就是有些教程里的cpptools）
* C/C++ Clang Command Adapter：提供静态检测（Lint），很重要
* Code Runner：右键即可编译运行单文件，很方便
# 其他可选扩展：
* Bracket Pair Colorizer：彩虹花括号
* Include Autocomplete：提供头文件名字的补全
* C/C++ Snippets：Snippets即重用代码块，效果自己百度；这个扩展安装量虽高，不过个人感觉用处实在不大，你也可以选择其他的Snippets扩展甚至自己定义
* One Dark Pro：大概是VS Code安装量最高的主题
* vscode-clangd：这个和Adapter二选一，出得比Adapter晚，下载量也低，但却是llvm官方出的。出现问题时可以换着试试