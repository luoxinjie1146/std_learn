# [RTTR](https://www.rttr.org/)

# 安装

## [安装Doxygen](https://blog.csdn.net/Q1302182594/article/details/51517880)

```
$ sudo apt-get install doxygen
$ sudo apt-get install graphviz
```

## 安装boost

### [linux下编译](https://blog.csdn.net/faihung/article/details/88128928)
```
$ sudo apt-get install mpi-default-dev
$ sudo apt-get install libicu-dev
$ sudo apt-get install python-dev
$ sudo apt-get install libbz2-dev
$ wget https://nchc.dl.sourceforge.net/project/boost/boost/1.66.0/boost_1_66_0.7z
$ 7z x boost_1_66_0.7z
$ cd boost_1_66_0.7z
$ ./bootstrap.sh
$ sudo ./b2
$ sudo ./b2 install
$ mkdir test
$ vi test.cpp
$ cat test.cpp
#include<iostream>
#include<boost/bind.hpp>
using namespace std;
using namespace boost;
int fun(int x,int y){return x+y;}
int main(){
    int m=1;int n=2;
    cout<<boost::bind(fun,_1,_2)(m,n)<<endl;
    return 0;
}
$ g++ test.cpp -o test
$ ./test
3
```

### 使用预编译版本

```
$ wget https://www.rttr.org/releases/rttr-0.9.6-src.tar.gz
```

### [Windows下编译](http://dreamphp.cn/blog/detail?blog_id=18774)

* 下载
  * [cmake下载](https://cmake.org/download/)
  * [boost下载](https://www.boost.org/users/download/)
  * [doxygen下载](https://www.doxygen.nl/download.html)
  * [rttr下载](https://www.rttr.org/download)
* [安装boost](https://blog.csdn.net/s_lisheng/article/details/72871218)
  * 打开vs开发人员命令提示
  * bootstrap.bat运行
  * 运行 b2.exe stage --toolset=msvc-14.0address-model=64 --stagedir="C:\boost\bin1.63.0\VC14.0"threading=multi --build-type=complete