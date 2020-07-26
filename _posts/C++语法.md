---
layout:     post   				    # 使用的布局（不需要改）
title:      C++语法 				# 标题 
subtitle:   记录一些刷题时常用的C++语法 #副标题
date:       2020-07-16 				# 时间
author:     fy 						# 作者
header-img: img/post-bg-2015.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 刷题
---
1. string substr (size_t pos = 0, size_t len = npos) const;
2. short：两字节，[-2^15, 2^15-1]，即 [-32768, 32767]；
int，long：四字节，[-2^31, 2^31-1]，即 [-2147483648, 2147483647] 2*10^9级， long long 9 *10^18级
3. string.find(substring)==string.npos表示未找到子串
4. map遍历
```
map<int, int>::iterator iter;
iter = _map.begin();
while(iter != _map.end()) {
    cout << iter->first << " : " << iter->second << endl;
    iter++;
}
```
5. 关于输入：

    cin>>tmp; 会将换行符和空格留在缓冲区，用cin.get()可以读取出来。
    
    要输入一行字符，以换行符结尾，可以用cin.getline(char tmp[],int len)，或者getline(cin, string str)，注意这时需要先将缓冲区的符号读取掉，否则会直接读取缓冲区符号。
    
    cin.get()会保留换行符，cin.getline会丢弃换行符
6. set.insert类似vector.push_back; 

    string &insert(int p0, int n, char c);//在p0处插入n个字符c

    string &insert(int p0,const string &s);——在p0位置插入字符串s

7. sort参数里自定义函数的构造，注意const
```
    bool test_sort(const test& n1, const test& n2){
        if(n1.score>n2.score) return 1;
        else if(n1.score==n2.score&&n1.reg<n2.reg) return 1;
        return 0;
    }
```