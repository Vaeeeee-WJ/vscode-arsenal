# 参考资料
- https://www.cnblogs.com/savo-shen/p/18312608
- https://blog.csdn.net/2301_77480632/article/details/155525078
- https://mountainatic.github.io/posts/stm32-modern-tools/

# STM32开发例程
- 安装STM32平台：QUICK ACCESS $\rightarrow$ Open $\rightarrow$ Platforms $\rightarrow$ Embeded $\rightarrow$ 搜索ST STM32 并安装，等待下载成功提示`Platform has been successfully installed`（会下载到`C:\Users\<用户名>\.platformio\ststm32`）
- 创建项目：Home $\rightarrow$  New Project $\rightarrow$ 填写项目信息
  
创建成功后项目目录含义如下：
| 目录名    | 含义/作用                                                          | 备注                                                                                                          |
| :-------- | :----------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------ |
| `.pio`    | 项目编译的过程文件(`.o文件`)和编译文件会存放在这。                           | 编译成功后的二进制文件（如 `.elf`、`.bin`、`.hex`）也在里面的 `build` 文件夹中。                              |
| `include` | 头文件存放位置，只有头文件（`.h`/`.hpp`）有效。                    | `include` 里的文件需要在项目配置文件（`platformio.ini`）中通过 `build_flags` 添加包含路径，否则编译器找不到。 |
| `lib`     | 库文件夹，用于存放一个个独立的库，每个库包含头文件和对应的源文件。 | 每个库可以单独建一个子文件夹放在 `lib` 目录下，PlatformIO 会自动递归扫描并编译。                              |
| `src`     | 源文件存放位置，只有源文件（`.c`/`.cpp`/`.s` 等）有效。            | 项目的入口文件（如 `main.c` 或 `main.cpp`）就放在 `src` 文件夹里。                                            |
| `test`    | 存放单元测试文件。                                                 | 配合 PlatformIO 的测试框架（如 Unity/Google Test）使用，用于编写和运行自动化测试用例。                        |
| `platformio.ini`    | 核心配置文件，所有板型选择、框架指定、编译宏、烧录设置都在这里改。                                                 |                  |


# TODO: platformio.ini文件字段解释