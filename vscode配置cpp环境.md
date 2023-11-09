# vscode配置cpp环境

## 1. 创建cpp文件

1. 创建文件夹，并在vscode中打开
2. 该文件夹中创建cpp脚本文件

## 2. 设置cpp编译选项

1. 鼠标点源文件内部，ctrl+shift+p选中==编辑配置==
2. 编译器路径选择==D:\mingw64\bin\gcc.exe==也就是gcc这个编译器
   intellisence选择==gcc-x64（legacy）==【这是代码提示工具】
   cpp的话，配置名称，添加配置，随便起个名字比如**c++**，编译器路径选择==D:/mingw64/bin/g++.exe==，也就是g++这个编译器
   intellisence选择==gcc-x64（legacy）==
   c语言标准选==c17==，c++标准选==c++17==
3. 操作后会默认生成.vscode这个文件夹，里面包含properties.json,这个文件会指定Windows的sdk、所用的编译器

## 3. 生成task.json文件

1. ==终端==->==配置任务==，选择==gcc.exe生成活动文件==
   cpp的话，选择==g++.exe生成活动任务==
2. 操作后默认生成了tasks.json文件，这个文件会指定编译器、指定被编译的文件、指定生成的可执行文件的路径

## 4. 编译和执行程序

1. 鼠标点击源文件，终端->运行生成任务（ctrl+shift+b）
2. 会生成.exe文件（这是个可执行程序）
3. 打开终端（ctrl+\~）后输入`.\test.exe`**注意这是文件名，根据自己的文件名更改**，回车执行即可

## 5. 另一个文件夹

1. 不用重新执行2、3步骤，.vscode文件夹可以直接copy到新的文件夹中

## 6. 编译多个文件的代码，修改tasks.json文件

1. 修改要生成的文件

~~~
"${file}",      //表示鼠标选中哪个文件就生成哪个文件
~~~

~~~
${workspaceFolder}\\*.cpp   //可以构建当前工作区中的所有c++文件
~~~

2. 修改输出文件名字，从而编译输出的文件名为：打开的工作区文件夹名字.exe

~~~
"${fileDirname}\\${fileBasenameNoExtension}.exe"
~~~

~~~
"${workspaceFolder}\\${workspaceRootFolderName}.exe"
~~~

## 7. vscode如何调试代码

1. 生成launch.json文件：

   运行和调试中点击创建launch.json文件，后弹出选项选择==C++(GDB/LLDB)==这个调试器选项【如果没有的话就回到某个源文件中编译一下，在右下角中的弹框中选择两次确定选项】
   然后.vscode中就会自动生成launch.json文件

2. 在launch.json文件中==添加配置==（右下角有选项），勾选==C/C++：（gdb）启动==

3. 修改自动生成的内容

   修改exe后缀的文件名添加到程序中

~~~
"program": "输入程序名称，例如 ${workspaceFolder}/a.exe",
~~~

例如修改成：

~~~
"program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
~~~

​				找到这个文件的路径

~~~
"miDebuggerPath": "/path/to/gdb",
~~~

修改成：

~~~
"miDebuggerPath": "D:\\mingw64\\bin\\gdb.exe",//路径应该是双斜杠，因为要转义一下
~~~

4. 开始调试

~~~
F5-启动调试
F10-逐过程调试
F11-逐语句调试
然后变量里面可以看变量的值
监视里边也可以自己添加变量用来监视，eg：a表示添加监视a，&a表示添加监视a的地址
~~~

细节调试过程自己训练