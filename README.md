# Import kubernetes C library as bazel Rule.

using ```rules_foreign_cc ```from bazel, this repo shows how kubernetes C client library (https://github.com/kubernetes-client/c) can be compiled and used as C library. 
```example``` folder contains bazel rule and sample C code.

## How to Run examples.
### Install pre-requisites
```bash
# Install pre-requisites
sudo apt-get install libssl-dev libcurl4-openssl-dev libwebsockets-dev uncrustify

# Build pre-requisite: libyaml
git clone https://github.com/yaml/libyaml --depth 1 --branch release/0.2.5
cd libyaml
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_TESTING=OFF  -DBUILD_SHARED_LIBS=ON ..
make
sudo make install
```
Assuming you have already installed bazel in your system, run:
```bash
bazel run //example:list_pod
```
If not bazel installed, install bazel and run the above command.

```bash
bazel version >=7.3.1
Works fine on Ubuntu >=22.04.5, centos and other linux platform supposed to work, but have not tried.
```
