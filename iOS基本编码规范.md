#iOS 基本编码规范
1. **格式化代码**:  
   1.1 指针*符号位置
       * 由于OC的语言特性,代码中需要大量使用到指针符号,为了规范化代码格式,建议所有的指针符号*都临近变量写,与数据类型之间保留一个空格.
       * 当指针符号出现在方法的返回值中或参数类型中时,指针符号应与数据类型之间保持一个空格
       * 建议写法:
       
       ```
       NSString *name;
       NSDictionary *dict;
       NSArray *dataArray;
       - (NSData *)dateWithString:(NSString *)str;
       ```
       
   1.2 赋值运算=的位置  
   
     * 代码中的赋值运算符在使用的时候,建议在 = 号的左右两边都各自保留一个空格.
     * 建议写法:

     ```
      int count = dataArray.count;
      NSDate *date = [NSDate date];
     ```
   
   1.3 +/- 与返回值位置
   
     * 在方法中,+和-与返回值之间,保留一个空格的位置,返回值与方法名之间不要有空格.
     * 若方法的参数较多,应每个参数独占一行,以冒号(:)垂直对齐.
     * 建议写法:

     ```
     + (NSString *)stringFromDate:(NSDate *)date;
     
     - (void)getDataWithURL:(NSString *)url
                    Dictionary:(NSDictionary *)paraDict 
                       Success:(MySuccessBlock)success
                       Failure:(MyFailuer)failuer{
                       .....
                       } 
     ```
     
 1.4 每行宽度
 
    * 15'MacBookPro每行最多不超过120个字符(以Xcode系统默认11号字体计算).
    * 13'MacBookPro每行最多不超过80个字符(以Xcode系统默认11号字体计算).
    * 通过 “Xcode => Preferences => TextEditing => 勾选 Page guide at column / 输入120或80 ” 来设置。  
2. **命名规范**
 * 代码中定义的变量名,常量名,类名(含分类名),方法名以及协议名等,建议使用驼峰命名法:即第一个出现的单词首字母小写,后面的单词首字母大写.

     ```
    int localVariableStr = 20;
     ```
 
 * 在项目中,类前缀应采用统一的项目名缩写的字母(一般为两个字母)
 * 代理名必须符合类名+Delegate的命名格式.
 * +方法名首个单词应与类名一致.
 * 自定义的初始化方法必须以initWith格式开头(注意W字母要大写,否则系统在给self赋值时会报错).
 * 类名首字母必须大写开头,方法名首字母必须小写开头.
 * 属性变量名最长不应超过20个字符.
 
3. **注释规范**:
 * 公开的属性和方法,必须进行注释.
 * 单行注释// 应写在注释代码的上一行 或本行代码后(注意要保留至少四个空格距离)
 * 若有多个单行注释与代码在同一行,注释应尽量垂直对齐.
 * 多行注释/* */,禁止多行注释嵌套多行注释.
 * 方法注释:
 
     ```
 /*方法描述: 初始化页面布局参数说明: 无返回结果: void*/
    ```
  
 * 逻辑判断应加注释.
 * 变量和常量应加注释. 
4. **Cocoa与Objective-C特性**:
  * 定义私有成员变量时,应将变量写在.m文件的匿名分类(延展)中.
  * 基本数据类型作为成员变量时,系统默认的初始值为0,注意避免重复初始化.
  * 引入框架文件时,使用import关键字,即便引入的是C语言头文件.
  * 初始化方法样例代码:

     ```
     - (instancetype)init {
                    if (self = [super init]) {
                    // write your code...
                    }
                    return self;
}
     ```
  * SETTER方法样例代码:

     ```
     - (void)setName:(NSString *)name{
                  _name = name;
               // write your code...
     }
     ```
  * GETTER方法样例代码:

     ```
     - (NSString *)name{
                 if (_name == nil){
                 // write your code...
               }
                 return name;
     }
     ```
5. **代理(委托)和Block(块代码)**
   * 代理类型的成员属性,使用关键字assign修饰.
   * Block类型的成员属性,使用关键字copy修饰.
   * 调用Block类型的代码,必须进行判断.
   * 调用代理方法必须调用response方法判断
   
6. **缩写列表**
  
   ------
   NSString   --------    Str  
   NSDictionary --------  Dict  
   NSArray -------- Arr  
   NSInteger -------- Int   
   NSData ------- Data  
   
   ------
 
 UILabel  -------   label  
 UIButton  -------- button  
 UIImage  -------- image  
 UITableView  ------- tableview  
 UITextView  ------- textview  
 UITextField  ------- textfield  
 UIImageView  ------- imageview   
 UIScorllView -------scrollview
 