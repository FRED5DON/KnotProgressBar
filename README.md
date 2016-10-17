# KnotProgressBar
A Custom View

**先上效果图**

![KnotProgressBar效果图](/forsee@2x.png "KnotProgressBar效果图")

###用法一 （不固定progress单位长度）
    即app:kpb_progress_cell_width无效
> 未设定固定宽时，按父级Layout `RelativeLayout`横向自适应[图一]

> 如果父级为`LinearLayout`, 需要自适应，应设置KnotProgressBar为`android:layout_width="match_parent"`

```xml
<com.freddon.android.app.knotprogressbar.KnotProgressBar
        android:id="@+id/kpb"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        app:kpb_background_label_font_color="@color/lightGray"
        app:kpb_background_progressbar_color="@color/lightGray"
        app:kpb_current_pos="2"
        app:kpb_horizontal_margin="15dp"
        app:kpb_knot_radius="10dp"
        app:kpb_label_font_color="@color/fontBlack"
        app:kpb_label_font_size="@dimen/H5"
        app:kpb_labels="待审核,待签约,待付款,已付款"
        app:kpb_progress_cell_height="4dp"
        app:kpb_progress_cell_width="80dp"
        app:kpb_progressbar_color="@color/hightLight"
        app:kpb_vertical_spacing="10dp" />
```

###用法二 （固定progress单位长度）
    即app:kpb_progress_cell_width生效
>1 父级Layout为 `LinearLayout`，属性设置`android:layout_width="wrap_content"`

>2 或设置`app:kpb_horizontal_extend="true"`

```xml
 <LinearLayout
        android:id="@+id/wrap"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true"
        android:layout_below="@+id/kpb"
        android:orientation="horizontal">

        <com.freddon.android.app.knotprogressbar.KnotProgressBar
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:kpb_background_label_font_color="@color/lightGray"
            app:kpb_background_progressbar_color="@color/lightGray"
            app:kpb_current_pos="2"
            app:kpb_horizontal_extend="false"
            app:kpb_knot_radius="10dp"
            app:kpb_label_font_color="@color/fontBlack"
            app:kpb_label_font_size="@dimen/H5"
            app:kpb_progress_cell_height="4dp"
            app:kpb_progress_cell_width="80dp"
            app:kpb_progressbar_color="@color/hightLight"
            app:kpb_vertical_spacing="10dp" />

    </LinearLayout>
```
###其他说明
####文字方向,是否垂直显示
```
app:kpb_label_vertical="true"
```
####label标签（逗号分隔，元素个数即为节点Knot个数）
>当没有标签时，需要设置节点数量，如`app:kpb_knot_count="5"`

```
app:kpb_labels="待审核,待签约,待付款,已付款"
```
####线高、线宽
```
app:kpb_progress_cell_height="4dp"
app:kpb_progress_cell_width="80dp"
```
####节点Knot半径
```
app:kpb_knot_radius="10dp"
```
####当前节点位置
```
app:kpb_current_pos="2"
```
####外边距 与*app:kpb_progress_cell_width*配合使用
```
app:kpb_horizontal_margin="15dp"
```
####文字与Knot边距
```
app:kpb_vertical_spacing="10dp"
```
####横向扩展（注：目前正在拓展嵌套ScrollView，解决中...）
```
app:kpb_horizontal_extend
```


