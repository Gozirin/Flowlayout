# FlowLayout

A FlowLayout for Android, which allows child views flow to next row when there is no enough space. The spacing between child views can be calculated by the FlowLayout so that the views are evenly placed.

<p align="center">
<img src="images/sample.png" width="360"/>
</p>


## Gradle

AndroidX:

```
implementation 'com.nex3z:flow-layout:1.3.3'
```

AppCompact:

```
implementation 'com.nex3z:flow-layout:1.2.4'
```


## Usage

```xml
<com.nex3z.flowlayout.FlowLayout
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:flChildSpacing="auto"
    app:flChildSpacingForLastRow="align"
    app:flRowSpacing="8dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SUN"/>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="MON"/>

    <!--...-->

</com.nex3z.flowlayout.FlowLayout>
```


## Attributes

| Attribute                | Format                       | Description                                                                                                                                          |
|--------------------------|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| flFlow                   | boolean                      | `true` to allow flow. `false` to restrict all child views in one row. The default is `true`.                                                         |
| flChildSpacing           | `auto`/dimension             | The horizontal spacing between child views. Either `auto`, or a fixed size. The default is 0dp.                                                      |
| flChildSpacingForLastRow | `auto`/`align`/<br>dimension | The horizontal spacing between child views of the last row. Either `auto`, `align` or a fixed size. If not set, `childSpacing` will be used instead. |
| flRowSpacing             | `auto`/dimension             | The vertical spacing between rows. Either `auto`, or a fixed size. The default is 0dp.                                                               |
| flRtl                    | boolean                      | `true` to layout child views from right to left. `false` to layout from left to right. The default is `false`.                                       |
| flMaxRows                | integer                      | The maximum height of FlowLayout in terms of number of rows.                                                                                         |

`auto` means that the actual spacing is calculated as per the size of the `FlowLayout` and the number of child views (or rows), so that the child views (or rows) are placed evenly.

`align` in `childSpacingForLastRow` means that the horizontal spacing of the child views in the last row keeps the same with the spacing used in the row above. If there is only one row in `FlowLayout` and the `childSpacingForLastRow` is set to `align`, this value is ignored and the actual spacing is calculated using `childSpacing`.


