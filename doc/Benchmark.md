## 题目 1

/clear
/set verbose
你好

```bash
Mac mini m4 llama3.1 LATEST
total duration:       1.905244583s
load duration:        83.973ms
prompt eval count:    12 token(s)
prompt eval duration: 437.84475ms
prompt eval rate:     27.41 tokens/s
eval count:           29 token(s)
eval duration:        1.376880876s
eval rate:            21.06 tokens/s

Mac mini m4 deepseek-r1 LATEST
total duration:       13.575743208s
load duration:        80.571292ms
prompt eval count:    3 token(s)
prompt eval duration: 596.513041ms
prompt eval rate:     5.03 tokens/s
eval count:           243 token(s)
eval duration:        12.707162874s
eval rate:            19.12 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=0
total duration:       3.2578926s
load duration:        158.1239ms
prompt eval count:    12 token(s)
prompt eval duration: 568.4899ms
prompt eval rate:     21.11 tokens/s
eval count:           23 token(s)
eval duration:        2.4731443s
eval rate:            9.30 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       1.9904175s
load duration:        173.5453ms
prompt eval count:    12 token(s)
prompt eval duration: 589.4521ms
prompt eval rate:     20.36 tokens/s
eval count:           11 token(s)
eval duration:        1.1923262s
eval rate:            9.23 tokens/s

Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=0
total duration:       28.9815462s
load duration:        74.1815ms
prompt eval count:    3 token(s)
prompt eval duration: 143.2477ms
prompt eval rate:     20.94 tokens/s
eval count:           211 token(s)
eval duration:        28.4781764s
eval rate:            7.41 tokens/s

Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       27.6481691s
load duration:        74.9475ms
prompt eval count:    3 token(s)
prompt eval duration: 136.1157ms
prompt eval rate:     22.04 tokens/s
eval count:           203 token(s)
eval duration:        27.1518336s
eval rate:            7.48 tokens/s
```



## 题目 2

/clear
/set verbose
Python 写一个插入排序

```bash
Mac mini m4 llama3.1 LATEST
total duration:       14.640359625s
load duration:        67.074125ms
prompt eval count:    17 token(s)
prompt eval duration: 547.7305ms
prompt eval rate:     31.04 tokens/s
eval count:           289 token(s)
eval duration:        13.987543624s
eval rate:            20.66 tokens/s

Mac mini m4 deepseek-r1 LATEST
total duration:       38.828586167s
load duration:        82.490958ms
prompt eval count:    8 token(s)
prompt eval duration: 721.929792ms
prompt eval rate:     11.08 tokens/s
eval count:           720 token(s)
eval duration:        37.554019863s
eval rate:            19.17 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=0
total duration:       30.0634379s
load duration:        95.09ms
prompt eval count:    17 token(s)
prompt eval duration: 354.0307ms
prompt eval rate:     48.02 tokens/s
eval count:           257 token(s)
eval duration:        29.3176776s
eval rate:            8.77 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       31.2378354s
load duration:        87.9647ms
prompt eval count:    17 token(s)
prompt eval duration: 389.2936ms
prompt eval rate:     43.67 tokens/s
eval count:           255 token(s)
eval duration:        30.2922361s
eval rate:            8.42 tokens/s

Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=0
total duration:       1m43.633757s
load duration:        68.308ms
prompt eval count:    8 token(s)
prompt eval duration: 356.9067ms
prompt eval rate:     22.41 tokens/s
eval count:           745 token(s)
eval duration:        1m42.235082s
eval rate:            7.29 tokens/s

Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       1m4.480255s
load duration:        73.9202ms
prompt eval count:    8 token(s)
prompt eval duration: 168.6102ms
prompt eval rate:     47.45 tokens/s
eval count:           473 token(s)
eval duration:        1m3.6476442s
eval rate:            7.43 tokens/s
```


## 题目 3

/clear
/set verbose
/set think
"""
有一天，一个女孩参加数学考试只得了 38 分。她心里对父亲的惩罚充满恐惧，于是偷偷把分数改成了 88 分。她的父亲看到试卷后，怒发冲冠，狠狠地给了她一巴掌，怒吼道：“你这 8 怎么一半是绿的一半是红的，你以为我是傻子吗？”女孩被打后，委屈地哭了起来，什么也没说。
过了一会儿，父亲突然崩溃了。
请问这位父亲为什么过一会崩溃了？
如果你实在想不出来可以直接回复不知道。
"""

```bash
# 没有正确解读
Mac mini m4 llama3.1 LATEST
total duration:       6.257216167s
load duration:        83.952125ms
prompt eval count:    162 token(s)
prompt eval duration: 1.984243917s
prompt eval rate:     81.64 tokens/s
eval count:           86 token(s)
eval duration:        4.170401672s
eval rate:            20.62 tokens/s

# 蒙圈了，强行解释了
Mac mini m4 deepseek-r1 LATEST
total duration:       6m14.557932708s
load duration:        188.4155ms
prompt eval count:    120 token(s)
prompt eval duration: 979.783041ms
prompt eval rate:     122.48 tokens/s
eval count:           6444 token(s)
eval duration:        6m8.856988622s
eval rate:            17.47 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=0
total duration:       7.2403995s
load duration:        95.0153ms
prompt eval count:    162 token(s)
prompt eval duration: 1.0138956s
prompt eval rate:     159.78 tokens/s
eval count:           52 token(s)
eval duration:        6.0021136s
eval rate:            8.66 tokens/s

Windows 3060 6G llama3.1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       4.602924s
load duration:        94.9034ms
prompt eval count:    162 token(s)
prompt eval duration: 1.0126049s
prompt eval rate:     159.98 tokens/s
eval count:           31 token(s)
eval duration:        3.426614s
eval rate:            9.05 tokens/s

Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=0


# 对不起，我实在想不出这位父亲为什么过一会儿会崩溃的原因。
Windows 3060 6G deepseek-r1 LATEST CUDA_VISIBLE_DEVICES=-1
total duration:       4.602924s
load duration:        94.9034ms
prompt eval count:    162 token(s)
prompt eval duration: 1.0126049s
prompt eval rate:     159.98 tokens/s
eval count:           31 token(s)
eval duration:        3.426614s
eval rate:            9.05 tokens/s
```