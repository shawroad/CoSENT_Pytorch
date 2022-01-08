# CoSENT_Pytorch

比Sentence-BERT更有效的句向量方案

## 
- 参考: https://github.com/bojone/CoSENT
- 对应博客：https://kexue.fm/archives/8847
- 孟子预训练模型: https://github.com/Langboat/Mengzi


## 实验结果
实验效果来了。 预训练模型用的是孟子, 学习率2e-5,batch_size=64,等价苏神代码中的batch_size=32. 只用了训练集训练，然后在测试集上做测试。 分别训练了5个epoch，使用斯皮尔曼系数评价

BQ数据集上的效果:
- Epoch:0 | corr: 0.710114
- Epoch:1 | corr: 0.722789
- Epoch:2 | corr: 0.714183
- Epoch:3 | corr: 0.713727
- Epoch:4 | corr: 0.712173

LCQMC数据集上的效果:
- Epoch:0 | corr: 0.779130
- Epoch:1 | corr: 0.785519
- Epoch:2 | corr: 0.786981
- Epoch:3 | corr: 0.785071
- Epoch:4 | corr: 0.784286

<b>苏神的结果:</b>
train训练、test测试：
| | ATEC | BQ | LCQMC | PAWSX | STS-B | Avg |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| BERT+CoSENT | **49.74** | **72.38** | 78.69 | **60.00** | **80.14** | **68.19** |
| Sentence-BERT | 46.36 | 70.36 | **78.72** | 46.86 | 66.41 | 61.74 |
| RoBERTa+CoSENT | **50.81** | **71.45** | **79.31** | **61.56** | **81.13** | **68.85** |
| Sentence-RoBERTa | 48.29 | 69.99 | 79.22 | 44.10 | 72.42 | 62.80 |

最终结果比苏神略低。在BQ上增幅明显，在LCQMC数据集上略低。 其他数据的实验  随后补上。

