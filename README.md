# 1 DynamicModuleLoader

DynamicModuleLoader is a C++ class that can load dynamic libraries on Windows and Linux platforms.

# 2 How to Use

```cpp
#include<iostream>

#include "DynamicModuleLoder.h"
typedef void(*Func_Add)(int,int);

int main()
{
	DynamicModuleLoder dllLoader;
	if (dllLoader.LoadDynamicModule("add.dll"))
	{
		void* voidTest = firstLoader.GetFunction("Add");
		if (voidTest != NULL)
		{
			Func_Add f_add = (Func_Add )(voidTest );
			int ret = f_add(1,2);
			std::cout << ret << std::endl;
		}
		else
		{
			std::cout << dllLoader.GetErrorMessage() << std::endl;
		}
	}
	else
	{
		std::cout << dllLoader.GetErrorMessage() << std::endl;
	}
	dllLoader.UnloadDynamicModule();
	getchar();

	return 0;
}
```
