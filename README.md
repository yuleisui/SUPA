# SUPA: Value-flow-based demand-driven pointer analysis

1. Download source code [SVF](https://github.com/SVF-tools/SVF)

2. Put `include`, `lib` and `tools` folders under the corresponding ones of SVF home directory
```
cp -r include $SVF_HOME
cp -r lib $SVF_HOME
cp -r tools $SVF_HOME
```
3. Put CMakeLists.txt under `SVF/lib/`
```
cp CMakeLists.txt $SVF_HOME/lib
```
4. Build SUPA following https://github.com/SVF-tools/SVF/wiki/Setup-Guide-(CMake)

5. Running SUPA with its executable `bin/dvf`

* 5.1 Flow-sensitive SUPA (querying points-to values of all pointers in a program)
```
dvf -dfs -query=all -flowbg=10000 example.bc
```
* 5.2 Flow- and context-sensitive SUPA (querying points-to values of all the function pointers in a program)
```
dvf -cxt -query=funptr -maxcxt=3 -flowbg=10000 -cxtbg=10000 example.bc
```

| Options       | Description           | 
| ------------- |:-------------:|
|-query | specify a set of queries for demand-driven analysis)|
|-dfs | flow- and field-sensitive analysis |
|-cxt | context-, flow- and field-sensitive analysis|
|-flowbg | flow-sensitive analysis budget (number of value-flow edges traversal)|
|-cxtbg | context-sensitive analysis budget (number of value-flow edges traversal)|
|-maxcxt | k-limiting context-sensitivity|
|-stat | print statistics|
|-print-query-pts | print points-to|


<br />
<br />

### Refererences:

Yulei Sui and Jingling Xue. [On-Demand Strong Update Analysis via Value-Flow Refinement](https://yuleisui.github.io/publications/fse16.pdf) ACM SIGSOFT International Symposium on the Foundation of Software Engineering (FSE '16) 

Yulei Sui, Ding Ye, and Jingling Xue. [Value-Flow-Based Demand-Driven Pointer Analysis for C and C++](https://yuleisui.github.io/publications/tse18.pdf) , IEEE Transactions on Software Engineering (TSE'18) 

<br />

