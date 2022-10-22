#include <fstream>
#include <iostream>  //cin and cout
#include <string>
#define filePath "hw1_input.txt"    //filename of the input file

//聲明一個命名空間，一個叫std的namespace，如果沒有的話之後的cout丟要改成std::cout
using namespace std;    

bool isDigit(string str){  //判斷是不是int
    int add = 0;  //變數去判斷現在有沒有負號
    if (str.length() == 0){return false;} //沒讀到東西
    if(str[0]=='-'){    //有讀到負號的話 --> add變成1，後面的迴圈會從負號後面開始跑
        add = 1;
    } 
    for (auto strIter = str.begin()+add; strIter != str.end(); strIter++) {  //auto可以用在不確定變數類型時
        if (!(isdigit(*strIter))){ //如果有一個不是數字的話 --> 回傳false
            return false;
        }
    }    
    return true;  //如果可以順利到結束的話 --> 全部都是數字 --> 回傳成功
}

bool isFloat(string str){  //判斷是不是float
    int add = 0;  
    bool dotFlag = false;  //判斷小數點有沒有出現過，T -> 有、F -> 沒有出現過 -->會影響最後的回傳值
    if (str.length() == 0){return false;}    
    if(str.at(0)=='-'){
        add = 1;  
    }   
    for (auto strIter = str.begin()+add; strIter != str.end(); strIter++) {      
        //如果遇到了'.' ，看點的前後有沒有數字 -> 如果前後沒有數字或是已經有點了 --> 就會出去  
        if (*strIter == '.' && !dotFlag && strIter != str.begin() && strIter != str.end() - 1){
            dotFlag = true;
        }
        else if (!(isdigit(*strIter))){    //如果不是數字的話 --> 回傳false
            return false;
        }
    }
    return true && dotFlag;  //如果有一個是0 --> 那結果還是會是0 (AND)
}

bool isID(string str){  //判斷是不是ID
    if (!isalpha(str.at(0))){return false;}  //如果第一個字元不是字母 --> 回傳false
    for (auto strIter = str.begin(); strIter != str.end(); strIter++){  
        //如果不是字母、底線、或是數字的話 --> 回傳false
        if (!isalpha(*strIter) && *strIter != '_' && !isdigit(*strIter)){  
            return false;
        }
    }
    return true;
}

int check(string str){
    if (str.at(str.length() - 1) != ';'){return 0;}  //Error                                 
    else {
        str.pop_back();
        if (isDigit(str)){return 1;}                 //Integer                                 
        if (isFloat(str)){return 2;}                 //Float                                
        if (isID(str)){return 3;}                    //Indentifier
    }
    return 0;
}

int main(){
    int count_Error = 0, count_Int = 0, count_Float = 0, count_ID = 0;
    string str_temp = "";
    fstream fin;   
    fin.open(filePath, ios::in);  //開檔
    while (getline(fin, str_temp)) {  //一行一行的抓資料
        switch (check(str_temp)) {  //印出順便計算有幾個
        case 0:
            cout << "Error: ";
            count_Error++;
            break;
        case 1:
            cout << "Integer: ";
            count_Int++;
            break;
        case 2:
            cout << "Float: ";
            count_Float++;
            break;
        case 3:
            cout << "Identifier: ";
            count_ID++;
            break;
        }
        cout << str_temp << endl;
    }
    fin.close();  //關檔
    //印出total計算的結果 
    cout << "----------Total number----------" << endl;
    cout << "Total Integer = " << count_Int << endl;
    cout << "Total Float = " << count_Float << endl;
    cout << "Total Identifier = " << count_ID << endl;
    cout << "Total Error = " << count_Error << endl;
}
