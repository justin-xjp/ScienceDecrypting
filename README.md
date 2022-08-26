## fork后

2022年8月，验证此库仍然可用。GH上目前有两个来源，具体差别是在于，科学文库似乎更改了PDF后面加密算法的名字，实际上CAJViewer 自己实现了一个 Encryption Filter，大概率只是 Adobe.PubSec 的魔改：

```
<</Length 40/SubFilter/TTKN.PubSec.s1/CF<</DefaultCryptFilter<</CFM/AESV2/Recipients[(AppendCA)]>>>>/Filter/TTKN.PubSec/StrF/DefaultCryptFilter/StmF/DefaultCryptFilter/EncryptMetadata true/R 2/V 2>>
```

感谢超理论坛的努力与付出：

[科学出版社图书全文下载方法--超理论坛](https://chaoli.club/index.php/2979/p2#p51440)

[科学文库PDF--超理论坛](https://chaoli.club/index.php/6542/0)

以下为原文

---

## Description
破解CAJViewer加有效期限制的文档，无损转为普通PDF格式文件，保留文字和目录，支持解密以下网站下载的文档：
- 科学文库 ( https://book.sciencereading.cn )
- 国家标准全文数据库 ( https://kns.cnki.net/kns8?dbcode=CISD / https://www.spc.org.cn/ )
- 其他，待验证...

## Usage

### 选择一：使用预编译的exe文件
在[Release页面](https://github.com/301Moved/ScienceDecrypting/releases)下载exe文件执行即可。

### 选择二：使用源码文件
1. 下载安装Python3 ( https://www.python.org/downloads/ )。
2. 下载源码库：点击右上角Code按钮并选择Download ZIP。下载完成后，完整解压压缩包，并进入解压文件夹，在文件夹地址栏输入cmd并回车以启动在当前目录下运行的cmd程序。
3. 安装依赖 。

在cmd窗口中运行以下指令。
```bash
pip3 install -U pip
pip3 install -r requirements.txt
```
4. 执行decrypt.py
```
Usage: python3 decrypt.py -i INPUT_FILE -o OUTPUT_FILE

Options:
  -h, --help            show this help message and exit
  -i FILE, --input=FILE  原始文件名
  -o FILE, --ouput=FILE  输出文件名

Example: python3 decrypt.py -i test.pdf -o test_dec.pdf
```

## 科学文库图书下载
大部分图书都可以通过国家[图书馆读者云门户](http://read.nlc.cn/outRes/outResList?type=%E7%94%B5%E5%AD%90%E5%9B%BE%E4%B9%A6)进行下载，少量无法下载的图书如果迫切需要可以提issue。
