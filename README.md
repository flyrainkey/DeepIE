# DeepIE: Deep Learning  for Information Extraction 

**DeepIE**： 基于深度学习的信息抽取技术（预计2020年8月31日前全部更新完毕）

## TOP 

- **知乎专栏文章下载**：[nlp中的实体关系抽取方法总结](https://github.com/loujie0822/DeepIE/blob/jielou/docs/实体关系抽取算法总结.md)

## Papers

- [ACL2020信息抽取相关论文汇总](https://github.com/loujie0822/DeepIE/blob/master/docs/ACL2020信息抽取相关论文汇总.md)
- [2019各顶会中的关系抽取论文汇总](https://github.com/loujie0822/DeepIE/blob/master/docs/2019各顶会中的关系抽取论文]汇总.md)
- [事件抽取论文汇总](https://github.com/loujie0822/DeepIE/blob/master/docs/事件抽取论文汇总.md)

## Codes

#### 1. 实体抽取

- **MSRA-NER**

| 方法                                         | f          | p          | r          |
| -------------------------------------------- | ---------- | ---------- | ---------- |
| char+ lstm-crf                               | 86.18%     | 88.43%     | 83.10%     |
| char-bigram + lstm-crf                       | 91.80%     | 92.60%     | 90.34%     |
| char-bigram + adTransformer-crf              | 92.98%     | 93.25%     | 92.72%     |
| char-bigram + lexion-augment + lstm-crf      | 93.33%     | 94.26%     | 92.43%     |
| char-bigram-BERT + lstm-crf                  | 94.71%     | 95.14%     | 94.27%     |
| char-bigram-BERT + lexion-augment + lstm-crf | **95.26%** | **95.90%** | **94.63%** |

- **CCKS2019-医疗实体抽取**

| 方法                                         | f          | p          | r          |
| -------------------------------------------- | ---------- | ---------- | ---------- |
| char-bigram + lstm-crf                       | 81.76%     | 82.91%     | 80.6       |
| + domain transfer（from ccks2018 to 2019）   | 82.54%     | 83.43%     | 81.81%     |
| char-bigram + adTransformer-crf              | 82.83%     | 82.19%     | 83.49%     |
| char-bigram + lexion-augment + lstm-crf      | 82.76%     | 82.79%     | 82.72%     |
| BERT-finetune+crf                            | 83.49%     | 84.11%     | 82.89%     |
| roBERTa-finetune+crf                         | 83.66%     | 83.67%     | 83.66%     |
| char-bigram-BERT + lstm-crf                  | 83.37%     | 83.51%     | 83.22%     |
| char-bigram-BERT + lexion-augment + lstm-crf | **84.15%** | **84.29%** | **84.01%** |

- **CCKS2020-医疗实体抽取**：

(注：测试集与ccks2019一致)

| 方法                                         | f          | p          | r          |
| -------------------------------------------- | ---------- | ---------- | ---------- |
| char-bigram + lstm-crf                       | 87.52%     | 87.19%     | 87.85%     |
| char-bigram-BERT + lstm-crf                  | 92.62%     | **92.46%** | 92.79%     |
| char-bigram-BERT + lexion-augment + lstm-crf | **92.78%** | 92.36%     | **93.20%** |

- **CCKS2020-面向试验鉴定的命名实体识别任务**：TODO

  

#### 2. 实体关系联合抽取

[具体使用说明](https://github.com/loujie0822/DeepIE/blob/master/docs/关系抽取run说明.md)

- 2019语言与智能技术竞赛：关系抽取任务 

| 方法                                       | f(dev)     | p(dev)     | r(dev)     |
| ------------------------------------------ | ---------- | ---------- | ---------- |
| multi head selection                       | 76.36      | 79.24      | 73.69      |
| ETL-BIES                                   | 77.07%     | 77.13%     | 77.06%     |
| ETL-Span                                   | 78.94%     | 80.11%     | 77.8%      |
| ETL-Span + word2vec                        | 79.99%     | 80.62%     | 79.38%     |
| ETL-Span + word2vec + adversarial training | 80.38%     | 79.95%     | 80.82%     |
| ETL-Span + BERT                            | **81.88%** | **82.35%** | **81.42%** |

- 2020语言与智能技术竞赛：关系抽取任务

| 方法            | f(dev) | p(dev) | r(dev) |
| --------------- | ------ | ------ | ------ |
| ETL-Span + BERT | 74.58  | 74.44  | 74.71  |



#### 3. 属性抽取

- **领域数据集：瑞金医院糖尿病信息抽取数据**

```
# 药物-属性
['药品-用药频率','药品-持续时间','药品-用药剂量','药品-用药方法','药品-不良反应']
# 疾病-属性
['疾病-检查方法','疾病-临床表现','疾病-非药治疗','疾病-药品名称','疾病-部位']
```

| 主体 | 方法                               | f     | p     | r     |
| ---- | ---------------------------------- | ----- | ----- | ----- |
| 疾病 | lstm+ multi-label pointer network  | 76.55 | 74.36 | 78.86 |
| 疾病 | bert + multi-label pointer network | 77.59 | 77.45 | 77.74 |
| 药物 | lstm+ multi-label pointer network  | 81.12 | 79.15 | 83.19 |



#### 4. 实体链接/标准化



#### 5.事件抽取

- **CCKS2020-医疗事件抽取**

- **CCKS2020：面向金融领域的篇章级事件主体抽取**

- **CCKS2020：面向金融领域的篇章级事件要素抽取**

  


#### 6.信息抽取中的低资源解决方案



## TODO-list

- [ ] 信息抽取领域的数据资源汇总：
  - 医疗
  - 金融
  - 电商
  - 法律
- [ ] 信息抽取相关竞赛汇总：
  - 百度-2020语言与智能技术竞赛：关系抽取任务
  - 百度-2020语言与智能技术竞赛：事件抽取任务
  - 百度-2019语言与智能技术竞赛：信息抽取
  - CCKS 2019 医疗命名实体识别
  - CHIP 2019 临床术语标准化任务
  - CCKS 2019 人物关系抽取
  - CCKS 2019 公众公司公告信息抽取
  - CCKS 2019 面向金融领域的事件主体抽取

- 摘要抽取

- 前沿技术在信息抽取中的应用

## Reference
