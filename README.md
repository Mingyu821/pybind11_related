# pybind11_related

This repository trails several bails of usage of pybind11...

### When meeting the lack of GLIBCXX***:

sudo find / -name "libstdc++.so*"

cd /home/mingyu/miniconda3/envs/temp/bin/../lib/

cp /usr/lib32/libstdc++.so.6.0.29 /home/mingyu/miniconda3/envs/temp/bin/../lib/

rm -rf libstdc++.so.6

ln -s libstdc++.so.6.0.29 libstdc++.so.6

strings /home/mingyu/miniconda3/envs/temp/bin/../lib/libstdc++.so.6 | grep GLIBCXX

### Compile operate.cpp:

g++ -O3 -Wall -shared -std=c++11 -fPIC `python3 -m pybind11 --includes` operate.cpp -o operate`python3-config --extension-suffix`

### When create setup.py:

python setup.py build_ext --inplace


