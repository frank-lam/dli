# Spark作业管理概述<a name="dli_01_0385"></a>

## 操作场景<a name="zh-cn_topic_0093946892_section31579140143928"></a>

Spark作业为在Spark作业编辑窗口中提交的作业。

Spark作业管理主要包括如下功能：

-   [重新执行作业](#section168728364416)
-   [查找作业](#section9242154518244)
-   [查看作业详情](#zh-cn_topic_0122090417_section15292102065813)
-   [删除作业](#zh-cn_topic_0122090417_section3753111385816)

## 作业管理页面<a name="section12526165519235"></a>

在总览页面单击“Spark作业”简介，可进入Spark作业管理页面。Spark作业管理页面显示所有的Spark作业，作业数量较多时，系统分页显示，您可以查看任何状态下的作业。

>![](public_sys-resources/icon-note.gif) **说明：**   
>作业执行成功后，作业记录只保存6小时。  

**表 1**  作业管理参数

<a name="zh-cn_topic_0122090417_table3950169215120"></a>
<table><thead align="left"><tr id="zh-cn_topic_0122090417_row2555468715120"><th class="cellrowborder" valign="top" width="16.07%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0122090417_p4021197415120"><a name="zh-cn_topic_0122090417_p4021197415120"></a><a name="zh-cn_topic_0122090417_p4021197415120"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="83.93%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0122090417_p3594448915120"><a name="zh-cn_topic_0122090417_p3594448915120"></a><a name="zh-cn_topic_0122090417_p3594448915120"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0122090417_row46758327132"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p16413434141957"><a name="zh-cn_topic_0122090417_p16413434141957"></a><a name="zh-cn_topic_0122090417_p16413434141957"></a>作业ID</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0122090417_p54419740141957"><a name="zh-cn_topic_0122090417_p54419740141957"></a><a name="zh-cn_topic_0122090417_p54419740141957"></a>所提交Spark作业的ID，由系统默认生成。</p>
</td>
</tr>
<tr id="zh-cn_topic_0122090417_row32873162171713"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p45480448171713"><a name="zh-cn_topic_0122090417_p45480448171713"></a><a name="zh-cn_topic_0122090417_p45480448171713"></a>作业名称</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0122090417_p18579134217227"><a name="zh-cn_topic_0122090417_p18579134217227"></a><a name="zh-cn_topic_0122090417_p18579134217227"></a>所提交Spark作业的名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0122090417_row31011923151038"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p10671857151038"><a name="zh-cn_topic_0122090417_p10671857151038"></a><a name="zh-cn_topic_0122090417_p10671857151038"></a>作业状态</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0122090417_p59114099151038"><a name="zh-cn_topic_0122090417_p59114099151038"></a><a name="zh-cn_topic_0122090417_p59114099151038"></a>作业的状态信息，包括如下。</p>
<a name="zh-cn_topic_0122090417_ul32930526154023"></a><a name="zh-cn_topic_0122090417_ul32930526154023"></a><ul id="zh-cn_topic_0122090417_ul32930526154023"><li>启动中：正在启动</li><li>运行中：正在执行任务</li><li>已失败：session已退出</li><li>已成功：session运行成功</li><li>恢复中：正在恢复任务</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0122090417_row36301606171658"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p14394959151048"><a name="zh-cn_topic_0122090417_p14394959151048"></a><a name="zh-cn_topic_0122090417_p14394959151048"></a>所属队列</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0122090417_p51238775151048"><a name="zh-cn_topic_0122090417_p51238775151048"></a><a name="zh-cn_topic_0122090417_p51238775151048"></a>所提交Spark作业所在的队列。</p>
</td>
</tr>
<tr id="zh-cn_topic_0122090417_row6424839516213"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p50569641162134"><a name="zh-cn_topic_0122090417_p50569641162134"></a><a name="zh-cn_topic_0122090417_p50569641162134"></a>创建时间</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0122090417_p18910361162145"><a name="zh-cn_topic_0122090417_p18910361162145"></a><a name="zh-cn_topic_0122090417_p18910361162145"></a>每个作业的创建时间，可按创建时间顺序或倒序显示作业列表。</p>
</td>
</tr>
<tr id="row1536633125019"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="p145363334505"><a name="p145363334505"></a><a name="p145363334505"></a>最后修改时间</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><p id="p153603315013"><a name="p153603315013"></a><a name="p153603315013"></a>作业运行完成的时间。</p>
</td>
</tr>
<tr id="zh-cn_topic_0122090417_row1662880815250"><td class="cellrowborder" valign="top" width="16.07%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0122090417_p475621615250"><a name="zh-cn_topic_0122090417_p475621615250"></a><a name="zh-cn_topic_0122090417_p475621615250"></a>操作</p>
</td>
<td class="cellrowborder" valign="top" width="83.93%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0122090417_ul181927155164"></a><a name="zh-cn_topic_0122090417_ul181927155164"></a><ul id="zh-cn_topic_0122090417_ul181927155164"><li>编辑：可修改当前作业配置，重新执行作业。</li><li>SparkUI：单击后，将跳转至Spark任务运行情况界面。<div class="note" id="note1149352315379"><a name="note1149352315379"></a><a name="note1149352315379"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p44941523123719"><a name="p44941523123719"></a><a name="p44941523123719"></a>状态为“启动中”的作业不能查看SparkUI界面。</p>
</div></div>
</li><li>终止作业：取消当前作业。</li><li>提交日志：查看提交作业的日志。</li><li>运行日志：查看运行作业的日志。</li><li>导出日志：将日志导出至OBS桶中。当作业状态在“运行中”时，不能导出日志。</li></ul>
</td>
</tr>
</tbody>
</table>

## 重新执行作业<a name="section168728364416"></a>

在“作业管理“页面，单击对应作业“操作”列的“重新执行“，跳转至“作业编辑器”页面，可根据需要修改参数，执行作业。

## 查找作业<a name="section9242154518244"></a>

在“作业管理“页面，选择“状态”和“所属队列”。系统将根据设置的过滤条件，在作业列表显示符合对应条件的作业。

## 查看作业详情<a name="zh-cn_topic_0122090417_section15292102065813"></a>

在“作业管理“页面，选中一条作业，单击该作业ID左侧的![](figures/icon-展开.png)或在“操作”列中单击“日志详情”，可查看该条作业的相关日志。

## 删除作业<a name="zh-cn_topic_0122090417_section3753111385816"></a>

在“作业管理“页面，单击“操作”列的“删除“，删除作业。

