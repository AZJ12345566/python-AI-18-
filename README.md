# python-AI-18-
python+AI笔记(18)
# 一阶-九章-自定义Python包
#包就是一个文件夹，在该文件下包含了一个__init__.py文件，该文件可用于包含多个模块文件，从逻辑上来看，包的本质依然是模块
#如果没有__init__.py文件，那么这个文件夹就是一个普通的文件夹

#在pycharm文件栏的根目录中，右键然后new，选择python package就可以创建一个python包了
#包可以通过import导入，也可以通过from语句来使用

#包的功能就是在逻辑上讲一批模块归位一类，方便使用

# 一阶-九章-安装第三方包
#第三方包安装很简单，只需要使用Python内置的pip程序即可
#格式是: pip install 包名称

# 一阶-九章-异常-模块-包-综合案例讲解
#字符串相关的模块
def str_reverse(s):
    return s[::-1]

def substr(s,x,y):
    #函数的功能是按照给定的下标完成给定字符串的切片
    return s[x:y]
if __name__='__main__':
    print(str_reverse("黑马程序员"))
    print(substr("黑马程序员",1,3))
    
#文件处理相关的工具模块
def print_file_info(file_name):
    #将给定路径的文件内容输出到控制台中
    f = None
    try:
        f = open(file_name,"r",encoding="UTF-8")
        content = f.read()
        print("文件的全部内容如下:")
        print(content)
    except Exception as e:
        print(f"程序出现异常了，原因是:{e}")
    finally:
        if f:  #如果变量是None，表示False，如果有任何内容，就是True
            f.close()

if __name__ = '__main__':
    print_file_info("D:/***.txt")

def append_to_file(file_name,data):
    open(file_name,"a",encoding = UTF-8)
    f.write(data)
    f.write("\n")
    f.close()

if __name__ = '__main__':
    print_file_info("D:/***.txt","bala")

# 一阶-十章-案例介绍

# 一阶-十章-JSON数据格式的转换
#JSON本质上来说就是带有特定格式的字符串
#如果有一种字符串按照指定的格式去组织和封装内容就是JSON字符串了
#JSON格式数据就是不同语言的中转站
#python和JSON是无缝转换的，字典啊，列表啊格式都是一样的

import json
data = [{"name":"长大山","age":11},{"name":"王大锤","age":13},{"name":"找小虎”,"age":16}]
json_str=json.dumps(data,ensure_ascii=False)  #第二个参数是不使用ascii码，将中文正确的输出
print(type(json_str))
print(json_str)

d = {"name":"周姐轮","addr":"台北"}
json_str = json.dumps(d,ensure_ascii=False)
print(type(json_str))
print(json_str)


s = [{"name":"长大山","age":11},{"name":"王大锤","age":13},{"name":"找小虎”,"age":16}]
l = json.loads(s)
print(type(l))
print(l)
