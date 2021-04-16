## CMAKE ISSUE with Ninja Multi Config minimal example
### to reproduce the issue
```
mkdir bug && cd bug;
git clone https://github.com/Haiderahandali/Cmake-issue-minimum-example;
cd Cmake-issue-minimum-example;
cmake -G"Ninja Multi-Config" -B build . ;
cmake --build build --config debug;
```
now edit the CMakeLists.txt
and run the command again 
```
cmake --build build --config debug
```


![gif of the issue](CmakeIssue.gif)

