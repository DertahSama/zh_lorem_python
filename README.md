# zh_lorem_python
用python生成中文假文（Chinese lorem），一个超简单的小函数。

# 功能
按给定字数或者给定原始文本生成对应长度的中文假文，以供排版检查等处使用。
![image](https://github.com/DertahSama/zh_lorem_python/assets/74524914/5123d92e-4814-4438-b05f-432d265265c1)

# 实现
从现代汉语语料词频表
- <http://www.moe.gov.cn/jyb_sjzl/ziliao/A19/201001/t20100115_75693.html>，或
- <http://corpus.zhonghuayuwen.org/Resources.aspx>

中的前500个中随机选词组成句子，并在随机位置插入标点符号和分段。
