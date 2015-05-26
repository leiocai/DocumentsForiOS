#ios代码开发规范补充（二）
1. 关于数字常量
 * 代码中使用的字面常量,尽量减少使用宏定义方式,推荐使用static const方式定义在文件预处理之后,@interface(或@implementation)之前.
 * 建议写法: 
  
     ```
     static const float ButtonWidth = 25.0;
     ```
  * 不推荐写法:
  
     ```
     #define kButtonWidth 25.0
     ```
2. 关于字符常量
  * 由于OC对C语言的兼容特性,在需要使用魔鬼数字时,建议使用char类型的字符进行代替,增加可读性.
  * 建议写法:
   
     ```
     UIButton *btn = [[UIButton alloc]init];
     btn.tag = 'login';
     ....
     
     ```
   
3. 关于property
   * 自定义类的属性时,建议每个property的修饰词之间保留一个空格.
   * 属性修饰词书写顺序建议为: nonatomic -> readonly / readwrite -> strong / weak / assign / id.  
   * property后与()之间不建议使用空格分离.
   * property的()后面建议添加一个空格后再跟上需要的数据类型定义.
   * 推荐写法:
   
     ```
     @property(nonatomic, readonly, strong) NSDictionary *dataDict;
     @property(nonatomic, copy) NSString *name;
     
     ```
   * 公有property推荐都进行详细注释.私有的property可酌情进行注释. 
   * 如果多行无需注释的property每行之间建议不要有空行(保持代码紧凑性).
   * 
4. 关于文件资源
   * 在Xcode的IDE中,图片文件建议放在Images.xcassets中.
   * 图片文件要自行先按类型组建好文件夹.
   * 文件资源推荐统一放在Supporting Files文件中.
   * 资源名称不建议使用中文.
  
5. 关于第三方框架
   * 引入的第三方框架数量较多时(5个及5个以上),建议使用Cocoapods进行管理.
   * 建议非UI类第三方框架(比如AFNetworking),进行必要的业务封装,以保证代码的简洁度.
   * 工程中的第三方框架应该集中在一个特定的文件夹中.
6. 
   


   