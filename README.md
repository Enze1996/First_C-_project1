Read me about this small C++ project below:

第一个交互式C++项目小结 (by REZ and GPT)

1，	以下命令行代码的主要功能是演示了如何使用C++编写一个简单的交互式程序，通过编译和链接多个源文件来组织代码，并展示了如何获取和处理系统时间。
 
 ![image](https://github.com/user-attachments/assets/16db0e20-3c72-40d5-be52-a205d4d70bee)
![image](https://github.com/user-attachments/assets/e74fd446-131f-4c90-b8b3-d429f4011956)
![image](https://github.com/user-attachments/assets/37b1ff77-02e0-443f-9813-cedbe50d8765)



2.  Makefile里的代码实现了一个简单的编译和链接过程，通过命令行工具调用编译器和链接器，从源文件生成目标文件，最后链接成可执行文件 time_test.exe。同时定义了清理操作，用于删除中间文件和可执行文件。
 ![image](https://github.com/user-attachments/assets/14445049-65de-44f0-99c7-bb93bb8adf88)

3. time.cpp
获取伦敦格林威治时间的代码：
#include "utils.h"
#include "time.h"
void PrintTime()
{
   std::time_t now = std::time(nullptr);
   std::cout << ", the time and date are " << std::asctime(gmtime(&now)) << std::endl;
}

修改后，获取当地的北京时间：
#include "utils.h"
#include "time.h"
void PrintTime()
{
    std::time_t now = std::time(nullptr);
    std::tm* localTime = std::localtime(&now); // 获取本地时间结构体指针

    if (localTime)
    {
        // 输出本地时间
        std::cout << ", the time and date are " << std::asctime(localTime) << std::endl;
    }
    else
    {
        std::cerr << "Failed to get local time!" << std::endl;
    }
}

4.整个项目执行前，界面如下：
 ![Uploading image.png…]()

命令行通过nmake运行makefile文件后：
 ![Uploading image.png…]()

直接可运行exe程序：
 ![Uploading image.png…]()

