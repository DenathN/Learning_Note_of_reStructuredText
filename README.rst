reStructuredText学习笔记
==============================

这是我的reStructuredText学习笔记，感觉语法比markdown复杂许多，表现手法也丰富许多吧应该，太难了，难的关键是文档太少，中文文档太少，并且写的都不是很清楚，看不太懂，只能一边看一边写reStructuredText验证它的语法，这样着实费时间，如果能将中文文档写的清楚，就不会让后学的人这么麻烦了

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**一、Docutils、Sphinx、reStructuredText简介**
#############################################################

Docutils、Sphinx、reStructuredText在Python社区中被广泛应用于文档的写作

很多python项目用它们来写作官方文档

例如：

    python

    Flask

    Scrapy

| **Docutils——Python社区的文档工具**

    Docutils是一个文档写作工具

    Docutils使用的轻量级标记语言叫做：reStructured Text
    
    以纯文本格式编写
    
    可以生成多种格式的文档
    
    官方网站：

| **Sphinx——基于Docutils的文档工具**

    可以生成更多种格式的文档

    不过注意这个Sphinx是一个文档编写工具而不是那个有名的全文检索引擎
    
    官方网站：

| **ReStructuredText——Docutils的标记语法**

    reStructuredText和Markdown类似，但是功能更为强大。

    简称：reST、ReST、RST

    扩展名：.rst

    渊源：历史上有一种轻量级文本标记语言——StructuredText

    含义：Docutils如此命名意为重新构建的文本

    哲学：
        Readable

        Unobtrusive

        Unambiguous

        Unsurprising

        Intuitive
        
        Easy

    官方网站：http://docutils.sourceforge.net/docs/user/rst/quickref.html

**二、环境搭建**
##################################################

1、安装python

2、配置python、python/scripts环境变量

3、安装docutils

    命令行中执行：pip install docutils

4、安装sphinx

    命令行中执行：pip install sphinx

**三、创建Sphinx项目**
##################################################

1、新建一个文件夹

2、命令行中进入该目录

3、命令行中执行：sphinx-quickstart

会显示：

::

    Welcome to the Sphinx 1.8.5 quickstart utility.
    
    #欢迎来到Sphinx1.8.5版本的快速启动实用工具

    Please enter values for the following settings 
    (just press Enter to accept a default value, if one is given in brackets).
    
    #请进入下面设置的值（如果小括号中给出一个值的话，按回车键即可表示接受）

    Selected root path: .
    
    #选择根路径

    You have two options for placing the build directory for Sphinx output.
    
    #你有两个选项去放置用于Sphinx输出的建造目录
    
    Either, you use a directory "_build" within the root path, 
    or you separate "source" and "build" directories within the root path.
    
    #你使用一个仓库"_build"在根路径，或者你分离"source"和"build"在根路径中

    > Separate source and build directories (y/n) [n]:
    
    #分离source和build目录（是/否） 默认为[否]：

此处按y，在根目录中分离"source"和"build"，方便管理

::

    Inside the root directory, two more directories will be created; 
    "_templates" for custom HTML templates and "_static" for custom 
    stylesheets and other static files.
    
    #在根目录中，将会创建2个额外的仓库，用于自定义HTML模板的"_templates"目录，
    和用于自定义样式表和其他静态文件的"_static"目录
    
    You can enter another prefix (such as ".") to replace the underscore.
    
    #你可以进入（键入、输入）另一个前缀（例如"."）去代替下划线
    > Name prefix for templates and static dir [_]:
    #命名一个用于模板目录和静态文件目录的目录名的前缀 默认为[_]：

此处按回车使用默认的“_”作为前缀，或者输入其他字符作为前缀，代替“_”，再按回车确定

::

    The project name will occur in several places in the built documentation.
    
    #项目名将会存在于被建立的文档中的几个地方
    
    > Project name:
    
    #项目名：

此处输入我们想用的项目名按回车即可

::

    > Author name(s):

    #项目名：

此处输入我们想用的作者名按回车即可

::

    > Project release []:

    #项目版本：

此处输入我们想用的项目版本号按回车即可，默认为

::

    If the documents are to be written in a language other than English, 
    you can select a language here by its language code.
    
    #如果文档是将要用英语之外的其他语言书写的，你可以在这里通过语言代码的方式选择一门语言。
    
    Sphinx will then translate text that it generates into that language.
    
    #Sphinx一会儿将会翻译它生成的那门语言的文本
    
    For a list of supported codes, 
    see http://sphinx-doc.org/config.html#confval-language.
    
    #支持的语言代码的列表，参见 http://sphinx-doc.org/config.html#confval-language
    
    > Project language [en]:
    
    #项目语言 默认为[en]：

此处输入我们如果用英语外的其他语言写文档的话，其他语言的语言代码，如果用英文按回车即可

::

    The file name suffix for source files.
    
    #源文件的文件名的后缀
    
    Commonly, this is either ".txt" or ".rst".
    
    #通常的，这个或者是".txt"或者是".rst"
    
    Only files with this suffix are considered documents.
    
    #只有带后缀的文件才会被认为（识别）是文档
    
    > Source file suffix [.rst]:
    
    #原文件后缀 默认为[.rst]

此处按回车使用默认的“.rst”作为后缀，或者输入".txt"作为前缀，再按回车确定

::

    One document is special in that it is considered the top node of the "contents tree", 
    that is, it is the root of the hierarchical structure of the documents.
    
    #一个文档，当它被认为是内容树的顶端节点，也就是说，它是文档的等级结构的根的时候，这个文档是特殊的
    
    Normally, this is "index", but if your "index" document is a custom template, 
    you can also set this to another filename.
    
    #一般情况下，这是一个“索引”，但是如果你的索引文档是一个自定义的模板，你也可以设置它为一个其他的文件名。
    
    > Name of your master document (without suffix) [index]:
    
    #你的主文档的名字（没有后缀） 默认为[index]

此处为主文档的名字，按回车使用默认的[index]主文档的名字，或者自定义一个文档名字

::

    Indicate which of the following Sphinx extensions should be enabled:
    
    #标明以下那个Sphinx扩展为可以使用的
    
    > autodoc: automatically insert docstrings from modules (y/n) [n]:
    
    #autodoc扩展：从module（模块）中自动的插入docstring
    （python自带的用于在注视中辅助显示模块信息的模块） （是/否） 默认为[否]

    > doctest: automatically test code snippets in doctest blocks (y/n) [n]:
    
    #doctest扩展：自动的测试代码片段在doctest（python自带的用于文档测试的模块）的块中 （是/否） 默认为[否]

    > intersphinx: link between Sphinx documentation of different 
    projects (y/n) [n]:
    
    #intersphinx扩展：在Sphinx文档记录和其他的项目之间建立链接 （是/否） 默认为[否]

    > todo: write "todo" entries that can be shown or hidden on build (y/n) [n]:
    
    #todo扩展：写可以被显示或隐藏在build上的todo入口 （是/否） 默认为[否]

    > coverage: checks for documentation coverage (y/n) [n]:
    
    #coverage扩展：为文档的coverage进行检查 （是/否） 默认为[否]

    > imgmath: include math, rendered as PNG or SVG images (y/n) [n]:
    
    #imgmath扩展：包括数学，以PNG或SVG图像的方式表达 （是/否） 默认为[否]

    > mathjax: include math, rendered in the browser by MathJax (y/n) [n]:
    
    #mathjax扩展： （是/否） 默认为[否]

    > ifconfig: conditional inclusion of content based on config 
    values (y/n) [n]:
    
    #ifconfig扩展： （是/否） 默认为[否]

    > viewcode: include links to the source code of documented 
    Python objects (y/n) [n]:
    
    #viewcode扩展： （是/否） 默认为[否]

    > githubpages: create .nojekyll file to publish the 
    document on GitHub pages (y/n) [n]:
    
    #githubpages扩展：创建.nojekyll文件去发布文档在GitHub页面上 （是/否） 默认为[否]

    A Makefile and a Windows command file can be generated 
    for you so that you only have to run e.g. 'make html' 
    instead of invoking sphinx-build directly.
    
    #一个Makefile和一个Windows命令文件可以为你生成从而你只需要运行，
    例如：'make html'，代替直接引用sphinx-build

    > Create Makefile? (y/n) [y]:
    
    #创建Makefile （是/否） 默认为[是]

    > Create Windows command file? (y/n) [y]:
    
    #创建Windows命令文件 （是/否） 默认为[是]

以上，由于对ReStructuredText不够了解，不知道说的什么意思，全部按默认执行了

::

    Creating file .\source\conf.py.
    Creating file .\source\index.rst.
    Creating file .\Makefile.
    Creating file .\make.bat.

    #

    Finished: An initial directory structure has been created.

    #

    You should now populate your master file 
    .\source\index.rst and create other documentation source files.
    Use the Makefile to build the docs, like so: 
    make builder where "builder" is one of the supported builders, 
    e.g. html, latex or linkcheck.

    #

4、命令行执行：make.bat html

会显示：

::

    Running Sphinx v1.8.5
    making output directory...
    building [mo]: targets for 0 po files that are out of date
    building [html]: targets for 1 source files that are out of date
    updating environment: 1 added, 0 changed, 0 removed
    reading sources... [100%] index
    looking for now-outdated files... none found
    pickling environment... done
    checking consistency... done
    preparing documents... done
    writing output... [100%] index
    generating indices... genindex
    writing additional pages... search
    copying static files... done
    copying extra files... done
    dumping search index in English (code: en) ... done
    dumping object inventory... done
    build succeeded.

    The HTML pages are in build\html.

说明转换html通过，会在该目录build目录下生成相应的html文件
我们进入目录下的build/html，使用浏览器打开index.html，查看页面效果

可以使用：

    make.bat html    #生成html格式的文档
    make html        #生成html格式的文档
    make.bat latex   #生成tex格式的文档
    make latex       #生成tex格式的文档

等命令输出rst文档

提示：
如果页面中文显示乱码，则有可能是因为index.rst是ANSI编码的，改用utf-8格式即可
注意rst文件编写如果不符合规则，make.bat的时候会提示报错信息，按照报错信息修改对应文件的对应行即可

**四、ReStructuredText语法**
##################################################

**内联元素/行内样式/行内元素/内联标记(inline element）**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**1、斜体:**
'''''''''''''''''''''''''''''''''''''''''''''''''''

单星号前后包围的是斜体

例如：

.. code::

    *这是斜体的样例*

会输出为：

*这是斜体的样例*

**2、粗体:**
'''''''''''''''''''''''''''''''''''''''''''''''''''

双星号前后包围的是粗体

例如：

.. code::

    **这是粗体的样例**

会输出为：

**这是粗体的样例**

**3、行内引用/行内代码块(inline literal):**
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

2个单引号前后包围的是行内引用、行内代码块

通常显示为等宽文本

例如：

.. code::

    ``这是行内引用、行内代码块的样例``

会输出为：

``这是行内引用、行内代码块的样例``

**4、反转义符：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

``\``

相当于反转义作用

reStructuredText可以利用反斜杠使符号成为普通符号，而不会被认为是reStructuredText语法符号而解析渲染

.. code::

    \*\*这不会是粗体\*\*

    \*这不会是斜体\*

会输出为：

\*\*这不会是粗体\*\*

\*这不会是斜体\*

消除空格：使用 \_ (脱字符和空格)代替空格作为分隔符，可以消除空格。

**5、链接：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

（1）独立链接：
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

reStructuredText会将网址、邮箱地址识别出来，自动转换为链接形式

例如：

.. code::

    https://github.com/DenathN

会输出为：

https://github.com/DenathN


（2）命名链接：
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

例如：

.. code::

    DenathN的GitHub主页_

    .. _DenathN的GitHub主页: https://github.com/DenathN

会输出为：

DenathN的GitHub主页_

.. _DenathN的GitHub主页: https://github.com/DenathN

如果想在命名链接后面继续写文本，可以加个转义符，然后接文本

例如：

.. code::

    DenathN的GitHub主页_\此处为继续写的文本

    .. _DenathN的GitHub主页: https://github.com/DenathN

会输出为：

DenathN的GitHub主页_\此处为继续写的文本

.. _DenathN的GitHub主页: https://github.com/DenathN

（3）指定链接
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A sentence with links to `Wikipedia`_ and the `Linux kernel archive`_.

.. _Wikipedia: https://www.wikipedia.org/
.. _Linux kernel archive: https://www.kernel.org/

（4）匿名链接
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Another sentence with an `anonymous link to the Python website`__.

__ https://www.python.org/

（5）我的版本为什么就不好用呢
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    指定链接

    一个句子带有链接到`维基百科`_和`linux内核`_

    .. _维基百科: https://www.wikipedia.org/
    .. _linux内核: https://www.kernel.org/

    匿名链接

    一个句子带有`python官网`__ 匿名链接

    __ https://www.python.org/

.. code::

    指定链接和匿名链接用重字符`\``括起来，而不是用引号``(')``括起来  `
    内联标记需要注意的地方：
        内联标记不能相互嵌套：**比如粗体中尝试嵌套*我想把这句话变成斜体*这样是不会嵌套斜体的**
        内联标记和内联标记中的文本之间不能有空格间隔，``* 此处是文本*`` 这样是不行的，会显示为* 此处是文本*
        当然，这些限制在未来版本可能会被改善

**6、图片：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

例如：

.. code::

    .. image:: https://avatars2.githubusercontent.com/u/40689539?s=400&u=22ad43459c953bdd0a873b072231afdb82ca2881&v=4
        :height: 100px
        :width: 100px
        :alt: funny cat picture
        :align: center

会输出

.. image:: https://avatars2.githubusercontent.com/u/40689539?s=400&u=22ad43459c953bdd0a873b072231afdb82ca2881&v=4
    :height: 100px
    :width: 100px
    :alt: funny cat picture
    :align: center





**块元素**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**1、代码块：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

可以使用无编程语言的代码块

例如：

.. code:: 

    if this is a paragraph of code,
    but no one knows which programming language it is 

可以指定支持高亮的编程语言的代码块

例如：

.. code:: python

    #例如这是一个python代码的代码块
    from bs4 import BeautifulSoup

**2、分割线、分隔线：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

例如：

.. code::

    ----

会输出

----


**3、标题**
'''''''''''''''''''''''''''''''''''''''''''''''''''

标题=上标题线、标题内容、下标题线

下标题线要大于等于标题内容的长度

上标题线可以省略，下标题线不可以省略
    
标题分6个等级，从1级到6级，标题显示出来的大小尺寸递减

可以使用以下符号作为标题线表示标题：

.. code::

    =
    -
    #
    ^
    '
    ~
    +
    *
    _
    \
    :
    "
    <
    >

reStructuredText标题解析、识别原理：
    reStructuredText并不规定哪种符号用来表示哪种标题
    
    但是同一篇文章中，不同等级的标题肯定用不同的符号表示，才不会造成混淆，导致解析错误，你说对吧
    
    当使用不同的符号表示标题的时候，reStructuredText会自动根据标题符号首次出现的顺序，分析出本篇文章的作者是使用哪一种符号表示哪一种标题
    
    并在后面的内容中依据此规则识别标题等级

reStructuredText推荐：
    
    文章开头使用1级标题作为本篇文章的主标题
    
    文章开头使用2级标题作为本篇文章的副标题
    
    文章正文中一般使用3~6级标题即可（如果3~6级不够，则也可使用2级标题，但1级标题只能作为文章唯一的主标题，出现在文章开头）


好吧，Denath习惯性的使用：

.. code::

    =作为主标题
    -作为副标题
    #作为一级标题
    ^作为二级标题
    '作为三级标题
    ~作为四级标题
    +作为五级标题
    *作为六级标题

**4、段落**
'''''''''''''''''''''''''''''''''''''''''''''''''''

段落是被空行分割的文字片段，左侧必须对齐，没有空格或者有相同多的空格

同一段落的行是左对齐的

左侧有空格会被视为缩进，缩进的段落被视为引用（引文）

同python一样，用相同缩进的方式表示处在同一个级别

例如：

.. code::

    这是第1段

    这是第2段

会输出为：

这是第1段

这是第2段

**5、无序列表/符号列表（Bullet list）：**
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

列表前后要空一行

可以使用以下符号加空格来表示：

``-``

``*``

``+``

例如：

.. code::

    - 第1条
        - 第1条的第1条
            - 第1条的第1条的第1条
                - 第1条的第1条的第1条的第1条
                    - 第1条的第1条的第1条的第1条的第1条
    - 第2条
    - 第3条

会输出为：

- 第1条
    - 第1条的第1条
        - 第1条的第1条的第1条
            - 第1条的第1条的第1条的第1条
                - 第1条的第1条的第1条的第1条的第1条
- 第2条
- 第3条

**6、有序列表/顺序列表/枚举列表（Enumerated list）：**
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

列表前后要空一行

可以使用以下符号配合特定格式来表示：

``阿拉伯数字: 1, 2, 3, ... (无上限)``

``大写字母: A-Z``

``小写字母: a-z``

``大写罗马数字: I, II, III, IV, ..., MMMMCMXCIX (4999)``

``小写罗马数字: i, ii, iii, iv, ..., mmmmcmxcix (4999)``

特定格式为：

``.后缀: 1. A. a. I. i.``

``()包起来: (1) (A) (a) (I) (i)``

``)后缀: 1) A) a) I) i)``

用#配合特定格式替代可自动编号

例如：

.. code::

    1. 第1条
        1. 第1条的第1条
            1. 第1条的第1条的第1条
                1. 第1条的第1条的第1条的第1条
                    1. 第1条的第1条的第1条的第1条的第1条
    2. 第2条
    #. 第3条

会输出为：

1. 第1条
    1. 第1条的第1条
        1. 第1条的第1条的第1条
            1. 第1条的第1条的第1条的第1条
                1. 第1条的第1条的第1条的第1条的第1条
2. 第2条
#. 第3条

**7、表格：**
'''''''''''''''''''''''''''''''''''''''''''''''''''

=====  =====  ======
   Inputs     Output
------------  ------
  A      B    A or B
=====  =====  ======
False  False  False
True   False  True
False  True   True
True   True   True
=====  =====  ======



=======  =======
aaaaaa   111111
bbbbb    2222222
cccc     3
aaaaaa   111111
bbbbb    2222222
cccc     3
=======  =======




















空行

可以使用Line Blocks增加空行，使单独一行中只有一个 | 符号即可 （前后都要有空行，因为它也是一个 块元素）

只要没有空行，不管换多少次行，都会处理为一行。 建议您将每行的内容控制在50个汉字或者100个字母之内， 尽量在标点符号处手动换行，以增加源文件的可读性。




**五、其他**
##################################################

更多其他标记，请参考文档
