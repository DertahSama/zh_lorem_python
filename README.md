# zh_lorem_python
用python生成中文假文（Chinese lorem），一个超简单的小功能。

# 功能
按给定字数或者给定原始文本生成对应长度的中文假文，以供排版检查等处使用。

例如，下面是「用假文测试翻译后latex排版效果」的应用，系从给定原始文本生成假文，并保留了原文中的公式（`$...$`环境）：
![image](https://github.com/DertahSama/zh_lorem_python/assets/74524914/5123d92e-4814-4438-b05f-432d265265c1)

# 实现方法
从《现代汉语语料词频表（教育部，2005）》
- <http://www.moe.gov.cn/jyb_sjzl/ziliao/A19/201001/t20100115_75693.html>
- 或<http://corpus.zhonghuayuwen.org/Resources.aspx>

的前500个词中，随机选词组成句子，并在随机位置插入标点符号和分段符号。

（吐槽一下，这官方语料库生成出来的假文都好官腔……）

# 使用例
- `.bynum()`方法生成一段给定字数的中文假文；
- `.fromen()`则根据给定空格分割文本生成中文假文，并且支持保留原文中的语句（就像上面的图片里那样，主要用于测试翻译后文本的排版）。
```python
lrm_zh=lorem_zh()
print(lrm_zh.bynum(200),'\n')
print(lrm_zh.fromen("never gonna let you down, \n never gonna make you cry".replace("gonna","xx01")).replace("xx01","gonna"))
```
> 学生教育文化作用人民完全作为物质起来。声图六会需要可能学校。并不她没物质。坐每中国一，干整个此结合这样斗争拿者次所以手日本与：第一建立
快；当较没有随着教育来为什么出这个内大家代表每：所谓。现在一定那个水东西他既：眼睛间以全方法拿，这时而是还日干部人们包括八！世界直接， 
现象吧第二五使用他们好外有它们先曾水平作品，就是按才能决定文化拿提高，吃水平水平呢；学眼睛正在可能办法。向小。年少地方劳动走部分图站指 
出。
> 
> 处gonna社会工作者、\
> 讲gonna与人们而是。

`.bynum()`方法中设置`multipars=1`来生成分段的长假文。
```python
print(lrm_zh.bynum(1000,multipars=1))
```
> 作为而然而！则这些话政策学全国而是思想有些打非但类：不是特点关于呀听因为完成有关。或建立此所先生他们因最最实际那些包括美国时至：已经不仅
无、内发展并岁它、名件农民间应结构她东西目前关于新出来人：变能力一切就是。部分制度性质正确回来声而是参加不过位看见然而句政府本？群众她好
上结构多社会主义实践看见。条件看见间系统、如果为了工作走最中国一样她有些民族应该和，觉得一个工业条数实验一点之关于政府。注意特点名决定坐
、不会部分分这里实现事有关造成写看到，谁。你政策参加及想眼睛等一切让类环境，并且正那地年就下来制度正确句、们如果时期不会文化工人斗争两，
写作农民产品环境关于社会主义分析相了问题，向呀又以及已指条少，当然产生有任务呀，的在过、规定大量经验种经济以小说方面？法同人民被个提高有
个方法。本制度很。同志元能有人、认为。
> 
> 位增加所谓要提高例如便四用出来基础，甚至你出现想看见由指意义，三人们认识现在虽然当然象行为分可能呀由。利用！不能当时并不。根据看到也条现
象虽然结构图任何现象少呢建设工作、正在时候它们然而它们。才能一点水平写时期可是几象：所以坐连这个种到较把引起又：甚至注意最少被经验过去带
文化。任务通过作品几、科学增加人们：知道不仅先单位二，下者个多一定结合具体每、又还有引起拿反映当然不过不能更再长内而那。各种。死受月：没
次因为任务能力并且教育头地位；应说岁根据运动原因起来反映感到变以基本不断人又，文化一起名之后行为天这因素一个该得青年各，非您这里党话还有
教育经验语言，干部教育一个可是社会主义看见建立工人根据会达到指出？低月好环境注意大量方面生活？结果成为联系增加然而但是：也就矛盾钱十分小
低商品总影响成为点：都过程表示他们任何您不仅要因；精神怎样本内有的先生、几原因历史！则此知道起地方才不是见：觉得反映企业当。
> 
> 需要法人们这里年上受到中国！先问将活动最在！自然时看着活动件人至等太更以及领导，应该主要有关十矛盾人民前；同志后来、而声利用那些时形式然
而打已起当然情况从作品。出心为什么方面道相所为什么看见不仅？十带要求啦事个人就是指还是元站创造。工业他们实践连作为再真党只，党与物质基础
老单位数甚至改变目前之后那些死看见最，出现；到。出现如果；为了认为！直接被这时政治大家大家应。成为政策创造会问题企业及看到此任务讲会这？
处活动名实践关于就是曾对人类这儿并不低会，这个再斗争觉得利用问题太曾。
