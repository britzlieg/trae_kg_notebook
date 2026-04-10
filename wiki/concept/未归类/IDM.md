## 标签

#数据防泄漏 #DLP #非结构化数据 #文档指纹 #信息安全

## 核心内容

IDM（索引数据匹配，Index Data Matching）是DLP中用于非结构化数据精准识别与保护的技术，通过生成文档指纹库并匹配相似度来防止机密文档泄露。

**技术原理：**
- 对敏感文档进行语义分析和分词
- 提取文档的指纹特征（使用滚动哈希算法）
- 生成指纹模型存储到指纹库
- 对被检测内容提取指纹进行匹配
- 计算相似度判断是否为敏感文档

**工作流程：**
1. 学习阶段：对敏感文档进行训练，生成指纹模型
2. 检测阶段：对传输或存储的内容提取指纹
3. 匹配阶段：与指纹库比对，计算相似度
4. 响应阶段：根据策略告警或阻断

**特点：**
- 支持部分匹配（10%-90%相似度）
- 可检测文档的不同版本或草稿
- 适用于Word、PPT、PDF等非结构化文档

## 通俗理解

IDM就像给每份重要文档发一张"身份证"。当你上传一份机密文件时，系统会分析它的内容特点，生成一个独特的"指纹"。之后如果有人想把这份文件或它的修改版发出去，系统会对比"指纹"，发现相似度很高就会拦截。即使文件被改了一些内容，系统也能识别出来，就像即使人换了发型，指纹还是能认出他是谁。

## 核心概念

- [[数据防泄漏]]
- [[DLP]]
- [[非结构化数据]]
- [[文档指纹]]
- [[EDM]]

## 引用

- [浅谈DLP数据防泄漏技术 - CSDN](https://blog.csdn.net/qq_33823833/article/details/136532864)
- [Using IDM to detect exact and partial file contents - Broadcom](https://techdocs.broadcom.com/us/en/symantec-security-software/information-security/data-loss-prevention/16-0/about-data-loss-prevention-policies-v27576413-d327e9/introducing-indexed-document-matching-idm-v27388119-d327e27601/using-idm-to-detect-exact-and-partial-file-contents-v83990410-d327e28291.html)
