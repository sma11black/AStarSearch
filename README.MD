## Visual Studio Configuration

### CMakeSettings.json
- Link显示乱码
> 解决方案管理器中右键CMakeLists.txt，更改CMake设置:
  generator: `Ninja` => `Visual Studio 15 2017`


```xml
x86:
"generator": "Visual Studio 15 2017",
"buildCommandArgs": "-m -v:minimal",
x64:
"generator": "Visual Studio 15 2017 Win64",
"buildCommandArgs": "-m -v:minimal",
```

### launch.vs.json
- 工作目录默认不是在当前目录下，而是在`C:\Users\你的用户名\CMakeBuilds\一串Hash\build\x64-Debug|x64-Release|x86-Debug|x86-Release`下面，程序运行的工作目录是在这个文件里面，对于文件读取的操作很麻烦
> 直接设置代码所在的目录为工作目录

```xml
"configurations": [
    {
	  ...,
      "currentDir": "${workspaceRoot}\\AStarSearch"
    }
  ]
```