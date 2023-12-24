# ORM基础

# 1.前置准备

## 1.1 ORM简介

ORM：对象关系映射（Object Relational Mapping）用于面向对象编程语言中，**不同类型的数据之间的转换**

ORM在**业务逻辑层**和**数据层**之间充当了**桥梁**作用

ORM 通过使用**描述对象和数据库之间的映射的元数据**，将程序中的对象自动持久化到数据库中。

![django-orm1](D:\MY_project\git\SCT-WangBo\OMR基础.assets\django-orm1.png)

## 1.2ORM优点

1. **简化数据库操作：**ORM工具提供了高级的抽象层，使开发人员能够使用面向对象的方式来处理数据库操作，而不需要直接编写和管理底层的SQL语句。这简化了数据库操作的过程，减少了开发人员的工作量。
2. 消除重复代码：使用ORM可以避免编写大量的重复性的数据库访问代码。ORM工具会自动生成数据库表格和SQL语句，使开发人员能够专注于业务逻辑而不是低层次的数据库细节。这样可以提高代码的可维护性和可读性。
3. **提高开发效率：**ORM工具提供了一组高级的API和工具，用于执行常见的数据库操作。这些工具使开发人员能够更快地开发数据库相关的功能，不需要手动编写大量的SQL语句和数据库访问代码。开发人员可以使用熟悉的面向对象编程语言来操纵数据，从而提高开发效率。
4. **跨数据库兼容性：**ORM工具**具有跨多种类型的关系型数据库的兼容性（OpenGauss无感替换）**。通过更改配置文件或设置，可以轻松地将应用程序从一种数据库切换到另一种数据库，而无需更改大量的代码。这提供了更大的灵活性和可扩展性。
5. **对象级别的数据操作：**ORM工具使开发人员能够以面向对象的方式操作数据。开发人员可以使用类和对象来表示和处理数据，而不是直接操作表格和行。这使得数据操作更加直观和易于理解。
6. **数据库独立性**：通过使用ORM，应用程序可以实现与特定数据库无关的代码。ORM工具处理数据库之间的差异，使开发人员能够编写通用的数据库访问代码，而不需要为每种数据库编写特定的代码。这提供了更大的可移植性和灵活性。

## 1.3ORM的缺点

1. **性能问题：**ORM框架在执行数据库操作时可能引入一定的性能开销。ORM工具需要将对象转换为数据库操作，这可能导致额外的查询和数据转换开销。在处理大量数据或复杂查询时，手动编写优化的SQL语句可能会比使用ORM更高效。
2. **复杂性和限制：**某些复杂的数据库操作可能在ORM框架中难以实现，或者需要编写复杂的查询语句。ORM框架试图提供一种通用的方式来处理各种数据库操作，但在某些情况下，直接使用原生SQL语句可能更为灵活和高效。
3. 隐藏的数据库细节：ORM工具抽象了底层数据库的细节，这在某些情况下可能导致开发人员对实际执行的SQL语句和数据库操作不够了解。这可能导致难以调试和优化性能问题。
4. **版本依赖性：**ORM框架通常会随着时间的推移进行更新和演进，可能会引入新的功能或更改现有的行为。这可能导致在升级ORM版本时需要进行一些修改和适应。
5. **不适用于非关系型数据库：**ORM框架主要设计用于关系型数据库，对于非关系型数据库（如NoSQL数据库）可能不是最佳选择。非关系型数据库通常具有不同的数据模型和查询方式，可能需要使用适用于该类型数据库的专门工具或库。

## 1.3ORM解析的过程

1. ORM将python代码转为SQL语句
2. SQL语句通过`pymysql`（使用MySQL数据库时）`postgresql-devel`和`install python3-devel`（使用OpenGauss）时传输数据到服务端
3. 在数据库中执行SQL语句并将结果返回

ORM与数据的对应关系

| ORM                           | 数据库              |
| :---------------------------- | :------------------ |
| Models类                      | 数据表              |
| Model对象                     | 表中的一行数据      |
| Model字段                     | 表中的列            |
| 字段类型                      | 列的数据类型        |
| 对象属性                      | 数据库列的值        |
| 关联字段（ForeignKey）        | 外键（foreign key） |
| 一对一关系（OneToOneField）   | 一对一关系          |
| 一对多关系（ForeignKey）      | 外键关联            |
| 多对多关系（ManyToManyField） | 中间表和关联表      |

## 1.4整体流程

1. **定义模型：**通过创建继承自`django.db.models.Model`的类来定义数据库模型。每个模型类代表一个数据库表。
2. **定义字段：**在模型类中定义字段，例如字符字段、整数字段、日期字段等。这些字段将映射到数据库表的列。
3. **执行迁移：**Django提供了迁移工具，用于根据模型的更改自动更新数据库模式。您可以使用`makemigrations`命令创建迁移文件，然后使用`migrate`命令将更改应用到数据库。
4. **创建对象：**使用模型类创建数据库对象的实例。您可以直接实例化模型类并设置属性，然后调用`save()`方法将对象保存到数据库。
5. **查询数据：**使用ORM的查询API执行数据库查询。您可以使用`objects`属性访问模型类的管理器，然后使用方法如`all()`、`filter()`和`get()`来过滤和检索数据。
6. **更新和删除数据：**通过修改对象的属性并调用`save()`方法来更新数据库中的数据。要删除数据，可以调用对象的`delete()`方法。
7. **关联关系：**Django ORM支持定义模型之间的关联关系，如一对一、一对多和多对多关系。通过在模型类中定义外键和多对多字段，您可以在模型之间建立关联。
8. **聚合和注解：**Django ORM提供了聚合函数和注解，用于执行复杂的查询操作，如计数、求和、平均值等。

## 1.5一些说明

1. 下面的学习将使用Django+MySQL作为案例

2. ORM可以操作数据表，但不可以操作数据库，因此数据库的创建需要开发者手动进行

   ```sql
   create database 数据库名称 default charset=utf8; # 防止编码问题，指定为 utf8

# 2快速体验

## 2.1创建Django项目，创建APP并注册

1. 创建Django项目

2. 终端执行命令创建APP
   ```python
   python manage.py startapp APP名称
   ```

   本次执行`python manage.py startapp web`

3. 在seetings.py中注册APP
   在`INSTALLED_APPS`中添加`web.apps.WebConfig`，也可直接添加`web`

   ```python
   INSTALLED_APPS = [
       'django.contrib.admin',
       'django.contrib.auth',
       'django.contrib.contenttypes',
       'django.contrib.sessions',
       'django.contrib.messages',
       'django.contrib.staticfiles',
       'web.apps.WebConfig'
   ]
   ```

4. 在seetings.py中配置数据库项

   将Django默认的数据库配置

   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.sqlite3',
           'NAME': BASE_DIR / 'db.sqlite3',
       }
   }
   ```

   改为

   ```python
   DATABASES = { 
       'default': 
       { 
           'ENGINE': 'django.db.backends.mysql',    # 数据库引擎
           'NAME': 'runoob', # 数据库名称
           'HOST': '127.0.0.1', # 数据库地址，本机 ip 地址 127.0.0.1 
           'PORT': 3306, # 端口 
           'USER': 'root',  # 数据库用户名
           'PASSWORD': '123456', # 数据库密码
       }  
   }
   ```

5. 使用pymysql或者mysqlclient链接数据库
   在与 settings.py 同级目录下的 `__init__.py` 中引入模块和进行配置

   ```python 
   import pymysql
   pymysql.install_as_MySQLdb()
   ```

   或者安装mysqlclient

   ```python
   pip install mysqlclient
   ```

6. 在创建的APP目录下的的model.py创建表并编写表结构
   ```python
   from django.db import models
    
   class Test(models.Model):
       name = models.CharField(max_length=20)
   ```

   - `CharField` ：表明类型，存储短文本
   - `max_length` ：设置长度最大值

   相当于在执行下面的SQL语句

   ```SQL
   CREATE TABLE test (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(20) NOT NULL
   );
   ```

7. 执行语句，创建表结构
   ```python
   python3 manage.py makemigrations  # 告诉Django我们的模型有变更
   python3 manage.py migrate  # 执行
   ```

8. 在urls.py中创建对应关系

   ```python
   from django.urls import path
    
   from web import views
    
   urlpatterns = [
       path('test/', views.test_db),
   ]
   ```

9. 进行测试
   ```python
   from django.http import HttpResponse
   from web.models import Test
   # 数据库操作
   def test_db(request):
       test1 = Test(name='the_name')
       test1.save()
       return HttpResponse("数据添加成功！")
   ```

# 3数据的增删改查

## 3.1 增加数据

```python
def creat_data(request):	
    对象名 = 类（表）名(name='runoob')
        对象名.save()
        return HttpResponse("数据添加成功！")
```

## 3.2 删除数据

```python
def delete_data(request):
    # 初始化
    response = ""
    
    # 根据条件过滤要删除的数据
    objects_to_delete = Test.objects.filter(name='the_name')
    
    # 删除数据
    objects_to_delete.delete()
    
    response = "数据删除成功！"
    return HttpResponse(response)
```

## 3.3修改数据



## 3.4查找数据

