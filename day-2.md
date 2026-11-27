# 学习Agent练习的个人笔记
我让AI帮我生成了Agent的学习计划，以后我将会根据学习计划去打造一个本地运行的Agent项目，供我调试使用。

###### 2026-11-27
-----------------------------------------------
1. 首先了解当前大模型的运行逻辑，以及Agent的框架组成，适当了解就好，脑袋里有一个大概的印象。
2. 配置环境，要学习Agent，那么就要安装Python 3.10+以上的版本，我本地电脑已有Python3.13。然后模型选择：①可选择线上任意模型，DeepSeek、智谱、Kimi等（免费付费都可）。②也可以选择开源模型部署在本地，使用Ollama。我选择第二种，安装完Ollama后，创建model文件夹，打开命令行，输入 “ollama pull qwen2.5:7b”，下载语言模型。模型的选择可将电脑配置提供给AI，让AI你选择，因为我是12G+32G,所以跑这个版本比较稳定。
3. 我的理解有点问题，Ollama的作用是将我下载的模型运行起来并且可以使用，我将模型下载到model文件夹中，这个模型只是一个文件无法直接使用，必须要下载到对应的Ollama（我本地电脑是这个：C:\Users\yzz\.ollama\models，后面要进行修改，不能占用c盘）文件夹下才可以。我之前的理解是，Ollama是一个中介的作用，只帮我下载模型。发现错误后，去B站看了学习视频，才了解Ollama的真正作用。
4. 要被自己笑死，忘记了计算机基本逻辑。虽然我是在model文件夹下运行CMD去下载模型，但是使用的还是Ollama，所以最终都回到默认下载路径下，与model文件夹无任何关系。
5. 先按照README.md文件的说明，使用命令行在当前文件夹运行了一下，没发现什么问题。后面要新建项目路径，使用Pycharm从0→1去开发这个项目。
6. 已经在Pycharm中创建好了新的项目，并且创建了好了对应的文件和文件夹。开始第一步编程，编写项目配置文件。

## 项目配置文件config.py
1. 首先是配置项目根目录，使用PROJECT_DIR = Path(__file__).resolve().parent.parent，去获取根目录，方便参数化，以及以后项目迁移。在这里学习到了，resolve()函数是获取当前文件夹的路径，它与根目录隔了几层，就加几个parent，最终就得到根目录。
2. 为了防止在使用的过程中，遇到中文乱码的问题，需要将终端的默认编码切换为utf-8。那么就需要修改三个标准流：sys.stdin标准输入，sys.stdout标准输出，sys.stderr标准错误。reconfigure方法就是修改这三个标准流中的编码。首先我们需要先判断reconfigure方法是否存在于这三个标准流中，需要调用hasattr(),存在就返回ture，然后调用，否则返回false。
```python
	def _user_utf8_everywhere():
    	for stream in (sys.stdin, sys.stdout, sys.stderr):
       		 if hasattr(stream,"reconfigure"):
            	stream.reconfigure(encoding="utf-8",errors="replace")

	_user_utf8_everywhere()
```

3.	hasattr(obj, name)方法是判断需要调用的函数在对象中是否存在，getattr(obj, name[, default])是直接调用对象中的函数，这两个通常配合使用，先确认在不在，再调用获取结果。
