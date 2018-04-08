# NLP 小课题
***
### 背景
当我们谈到一个公司的时候，或在网上检索一个公司信息的时候，我们常常利用这家公司的别名或简称。
例如，我们对【招商银行股份有限公司】一般会说【招商银行】【招行】等，因为这些简称往往在一定程度指代了该公司。 但是，我们可能不会说【招商】代表【招商银行股份有限公司】，因为还有【招商证券股份有限公司】【招商局集团有限公司】等会引起歧义，因此【招商】对【招商银行股份有限公司】的代表性就降低了，可能只有20%，而【招商银行】有90%【招行】80%（暂且不关注这个比例的科学性，仅仅示例）。
因此，我们希望通过一种较通用的方法，能够给出任何一家公司的几个候选简称，让这些候选简称能够一定程度代表该公司，且给出这些简称的代表性相对排序，例如【招商银行股份有限公司】的简称【招商银行】>【招行】>【招商】。

### 问题
请尝试给出一种方法或思路，对任何一个公司名称，都能返回该公司的候选简称（每个公司候选简称个数可能不一样），且按相关性大小排序。 
相关性大小可以通过人工经验来简单验证，方法不限。

### 思路
1. 将公司名字分词
2. 通过计算各词的TFIDF，去掉TFIDF过低的一些词，并选出各公司名的一个关键词
3. 列出所有包含该关键词的公司名简称组合
4. 按照所有词组合的TFIDF的和将各简称组合进行排序
5 输出到csv文件

### 使用的NLP library
#### thulac

> THULAC（THU Lexical Analyzer for Chinese）由清华大学自然语言处理与社会人文计算实验室研制推出的一套中文词法分析工具包，具有中文分词和词性标注功能。

github: https://github.com/thunlp/THULAC-Python

### 文件夹内文件说明
nlp_project.py: 运行代码

NLP小课题.xlsx: 输入文件

user_dict.txt: 用于分词的用户自定义词典，主要词汇为:

- 行业名称

- 世界各国名字

- 中国县级以上单位名称
