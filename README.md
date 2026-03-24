安装 protobuf-3.21.12 步骤：

1. clone
```shell
git clone git@github.com:cenxiaowei2004/protobuf-3.21.12.git

tar -xvf protobuf-3.21.12.tar 

cd protobuf-3.21.12
```

2. make
```shell
./configure --prefix=/usr/local/protobuf

make

# 遇到错误，可直接跳过该步：
sudo make check

sudo make install
```

3. config
```shell
sudo vim /etc/profile
# 添加内容如下：
# protobuf:
# (动态库搜索路径) 程序加载运行期间查找动态链接库时指定除了系统默认路径之外的其他路径
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/protobuf/lib/
# (静态库搜索路径) 程序编译期间查找动态链接库时指定查找共享库的路径
export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/protobuf/lib/
# 执行程序搜索路径
export PATH=$PATH:/usr/local/protobuf/bin/
# c程序头⽂件搜索路径
export C_INCLUDE_PATH=$C_INCLUDE_PATH:/usr/local/protobuf/include/
# c++程序头⽂件搜索路径
export CPLUS_INCLUDE_PATH=$CPLUS_INCLUDE_PATH:/usr/local/protobuf/include/
# pkg-config 路径
export PKG_CONFIG_PATH=/usr/local/protobuf/lib/pkgconfig/
```
