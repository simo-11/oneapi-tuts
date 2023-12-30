# oneAPI installation

## register, initial online installer download and install
https://www.intel.com/content/www/us/en/developer/tools/oneapi/base-toolkit-download.html?operatingsystem=window&distributions=online
Size	17.20 MB
Version	2024.0.1
"C:\Users\simon\Downloads\w_BaseKit_p_2024.0.1.45.exe"

https://www.intel.com/content/www/us/en/docs/oneapi-base-toolkit/get-started-guide-windows/2024-0/overview.html

C:\Program Files(x86)\Intel\oneAPI

Full install, download 2.7 GB, required space 16.6

Custom install shown components
![image](https://github.com/simo-11/oneapi-tuts/assets/1210784/f062d97f-8e68-40c7-a9b6-de1646384ea8)

![image](https://github.com/simo-11/oneapi-tuts/assets/1210784/fa3379fe-124d-4962-9cee-a36b13ce9df9)

## Configure

file:///C:/Program%20Files%20(x86)/Intel/oneAPI/basekit/2024.0/readme-get-started-windows-base-kit.html
https://www.intel.com/content/www/us/en/develop/documentation/get-started-with-intel-oneapi-base-windows/top/before-you-begin.html

CMake was already installed using winget

## Personal account 
part of documention requires logging in using personal account

## Documentation
https://www.intel.com/content/www/us/en/developer/articles/guide/download-documentation-intel-oneapi-toolkits-components.html
https://www.intel.com/content/www/us/en/developer/tools/oneapi/documentation-library.html

## Test install
https://www.intel.com/content/www/us/en/docs/oneapi-base-toolkit/get-started-guide-windows/2024-0/overview.html

### Setup and get code for sample
```
> cmd.exe "/K" '"C:\Program Files (x86)\Intel\oneAPI\setvars.bat" && pwsh'
openapi-tuts> oneapi-cli.exe
(1) Create a project
(1) cpp
Toolkit
Get Started
Base: Vector Add
oneapi-tuts> echo "**/build-using*" >>.gitignore
```
### Build and run buffers-version
```
oneapi-tuts\vector-add> mkdir build-using-buffers
oneapi-tuts\vector-add\build-using-buffers> cmake -G "NMake Makefiles" ..
build-using-buffers> nmake cpu-gpu
build-using-buffers> Measure-Command {.\vector-add-buffers.exe | Out-Default}
Running on device: Intel(R) UHD Graphics
Vector size: 10000
[0]: 0 + 0 = 0
[1]: 1 + 1 = 2
[2]: 2 + 2 = 4
...
[9999]: 9999 + 9999 = 19998
Vector add successfully completed on device.

Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 948

```
### Build and run usm-version
```
> md build-using-usm
vector-add\build-using-usm> cmake -G "NMake Makefiles" .. -DUSM=1
vector-add\build-using-usm> nmake cpu-gpu (5 seconds)
```

### Visual studio integration
https://www.intel.com/content/www/us/en/docs/oneapi-base-toolkit/get-started-guide-windows/2024-0/run-a-sample-project-using-an-ide.html

Debugging is not explained

### visual studio code integration
https://www.intel.com/content/www/us/en/docs/oneapi-base-toolkit/get-started-guide-windows/2024-0/run-a-sample-project-with-vscode.html
