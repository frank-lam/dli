# 提交SQL作业<a name="dli_01_0002"></a>

帮助用户快速开始使用DLI提交SQL作业查询数据。基本流程如下：

[步骤1：登录华为云](#section3751181910618)

[步骤2：上传数据至OBS](#section61379418181550)

[步骤3：进入DLI SQL作业编辑器](#section19012773105034)

[步骤4：创建队列](#section10742144985011)

[步骤5：创建数据库](#section21433273112656)

[步骤6：创建表](#section21590507141153)

[步骤7：查询数据](#section37788816112733)

如下操作以查询OBS的数据为例，DLI的数据查询操作类同。

## 步骤1：登录华为云<a name="section3751181910618"></a>

使用DLI服务，首先要登录华为云。

1.  打开[华为云](https://www.huaweicloud.com/)首页。
2.  在登录页面输入“账户名“和“密码“，单击“登录“。

## 步骤2：上传数据至OBS<a name="section61379418181550"></a>

DLI可以查询来自OBS的数据，查询数据前，需要在OBS中上传数据文件。

1.  在华为云页面的上方导航栏中，选择“产品“。
2.  在“基础服务“列表中，单击“存储”中的“对象存储服务OBS”。
3.  在OBS服务产品页，单击“管理控制台“，进入OBS管理控制台页面。
4.  创建一个桶，桶名全局唯一，这里以桶名“obs1”为例。
    1.  单击“创建桶“。
    2.  进入“创建桶”页面，选择“区域”，输入“桶名称”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >创建OBS桶时，需要选择与DLI管理控制台相同的区域，不可跨区域执行操作。  

    3.  单击“立即创建”。

5.  单击所建桶“obs1”，进入“概览”页面。
6.  单击左侧列表中的“对象”，选择“上传文件”，将需要上传的文件“sampledata.csv“上传到指定目录，单击“确定“。

    文件上传成功后，待分析的文件路径为“s3a://obs1/sampledata.csv“。


## 步骤3：进入DLI SQL作业编辑器<a name="section19012773105034"></a>

使用DLI进行数据查询，需要先进入SQL作业编辑器。

1.  在华为云页面的上方导航栏中，选择“产品“。
2.  在“EI企业智能“列表中，单击“大数据“\>“大数据计算“中的“数据湖探索 DLI“。
3.  在DLI服务产品页，单击“进入控制台“，进入DLI管理控制台页面。
4.  单击总览页面“SQL作业”框或其右侧的“创建作业”，可进入SQL作业“作业编辑器”页面。

## 步骤4：创建队列<a name="section10742144985011"></a>

队列是使用DLI服务的基础，执行SQL作业前需要先创建队列。

-   DLI有预置的可用队列“default“。若使用default队列，将按照扫描量计费。
-   用户也可根据需要自己创建队列。使用自建队列，将按照CU时或包年包月计费。
    -   创建队列详细介绍请参考[创建队列](创建队列.md)。
    -   具体计费方式请参考[《数据湖探索价格说明》](https://support.huaweicloud.com/price-dli/dli_06_0000.html)。


## 步骤5：创建数据库<a name="section21433273112656"></a>

在进行数据查询之前还需要创建一个数据库，例如db1。

>![](public_sys-resources/icon-note.gif) **说明：**   
>“default”为内置数据库，不能创建名为“default”的数据库。  

在“作业编辑器”页面右侧的编辑窗口中，输入如下SQL语句，单击“执行”。阅读并同意隐私协议，单击“确定”。

**create database db1;**

数据库创建成功后，新建的数据库db1会在左侧“数据库“列表中出现。

>![](public_sys-resources/icon-note.gif) **说明：**   
>在DLI管理控制台第一次单击“执行”操作时，需要阅读隐私协议，确认同意后才能执行作业，且后续“执行”操作将不会再提示阅读隐私协议。  

## 步骤6：创建表<a name="section21590507141153"></a>

数据库创建完成后，需要在数据库db1中基于OBS上的样本数据“s3a://obs1/sampledata.csv“创建一个表，例如table1。

1.  在“作业编辑器“页面右侧的编辑窗口上方，选择队列“default”和数据库“db1”。
2.  在编辑窗口中，输入如下SQL语句，单击“执行”。

    **create table table1 \(id int, name string\) using csv options \(path 's3a://obs1/sampledata.csv'\);**

    表table1创建成功后，单击左侧![](figures/icon-数据库.png)，再单击db1，新创建的表table1会在“表“区域下方显示。


## 步骤7：查询数据<a name="section37788816112733"></a>

完成以上步骤后，就可以开始进行数据查询了。

1.  在“作业编辑器“页面左侧的“表“区域，选择新创建的表table1，双击表，在右侧编辑窗口中，自动输入SQL查询语句，例如查询table1表的1000条数据：

    **select \* from db1.table1 limit 1000;**

2.  单击“执行”，系统开始查询。

    SQL语句执行成功后，可在SQL作业编辑窗口下方查看查询结果。

    **图 1**  查询结果<a name="fig3046654105458"></a>  
    ![](figures/查询结果.png "查询结果")


