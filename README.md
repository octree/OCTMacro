# Objective-C 设置属性，转换成链式调用

## 支持类型
1. NSUInteger
2. double
3. CGRect
4. CGSize
5. NSTimeInterval
6. CGPoint
7. CGFloat
8. NSInteger
9. BOOL
10. id
11. NSString
12. NSMutableString
13. NSNumber
14. NSArray
15. NSMutableArray
16. NSDictionary
17. NSMutableDictionary
18. NSURL
19. NSData
20. NSMutableData
21. NSDate

*注：可添加自定义类型

## Usage

```objectivec
typedef void (^OCTCustomBlock) (NSInteger num);

//  默认类型的支持
auto_declare_block(Test)

//  添加对自定义类型的支持
declare_block_no_asterisk(Test, OCTCustomBlock)

@interface Test : NSObject

@property (nonatomic) NSInteger num;
@property (copy, nonatomic) NSString *string;
@property (copy, nonatomic) OCTCustomBlock code;

//  声明方法
///  ClassName PropertyType propertyName

declare_method(Test, NSString, string)
declare_method(Test, NSInteger, num)
declare_method(Test, OCTCustomBlock, code)

@end

@implementation Test

//  方法实现
imp_method_no_asterisk(Test, NSInteger, num)
imp_method_asterisk(Test, NSString, string)
imp_method_no_asterisk(Test, OCTCustomBlock, code)

@end


test.oct_num(100).oct_string(@"hello")

```
