#C语言常见错误（个人整理 ）
  
##&nbsp;&nbsp;scanf()
<p>&nbsp;&nbsp;&nbsp;传递的应该是变量的**地址**而非变量本身，错误使用会造成引用坏指针的错误</p>
```
    1) scanf("%d",&val); (√)
    2) scanf("%d",val);  (x)
```
##&nbsp;&nbsp;不安全的函数
<p>&nbsp;&nbsp;&nbsp;使用不安全的函数时应当注意避免**栈溢出**，尽量使用它的安全版本;</p>
<p>&nbsp;&nbsp;&nbsp;常见不安全的有strcpy,sprintf等</p>
```
    1) fgets(buf,bufsize,fp); (√)
    2) gets(buf);  (x)
```
##&nbsp;&nbsp;指针大小
<p>&nbsp;&nbsp;&nbsp;指针与它所指向的数据不一定具有相同大小</p>
```
    1) int **A = (int **)malloc(n*sizeof(int*)); (√)
    2) int **A = (int **)malloc(n*sizeof(int))  (x)
```
