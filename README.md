# Scanner-like-lex

 ```note:
- [ ] scanner.cpp是有判斷
-0 -> int, 01.23 -> error, 0.23 -> float, +111 -> error, 0 -> int, 01234 -> error
- [ ] scanner_version2.cpp -> 是判斷
-0 -> int, 01.23 -> float, 0.23 -> float, +111 -> error, 0 -> int, 01234 -> int```

### 使用方法
1. 在一開始define的地方寫上input.txt的檔名
```cpp=
#define filePath "hw1_input.txt"
```
2. 將scanner.cpp檔跟input.txt檔放入同一個資料夾中
3. 建議使用visual studio code去編譯，直接按run code即可


### 規則部分
```
數字(int) -->(前面可能有-號)，其餘全部必須是數字，結尾要用';'+'\n'
浮點數(float) -->(前面可能有-號)，其餘全部必須是數字，且'.'前後至少有一位數字，結尾要用';'+'\n'
變數(ID) --> 第一個字必須是字母，後面可接字母、數字、底線，結尾要用';'+'\n'
```
![image](https://user-images.githubusercontent.com/92772248/197323595-75ca2902-ede1-4a7a-8511-27de45523c0f.png)
