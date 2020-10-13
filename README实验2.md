# Android界面布局实验报告
## 1.线性布局
- 代码如下：
    - xml代码：
```XML
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity"
    >
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_weight="10"
        android:orientation="horizontal">
    <Button
        android:id="@+id/button_1"
        android:layout_width="120dp"
        android:layout_height="60dp"
        android:text="ONE"
        />
    <Button
        android:id="@+id/button_2"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:text="TWO"
        />
    <Button
        android:id="@+id/button_3"
        android:layout_width="140dp"
        android:layout_height="60dp"
        android:text="THREE"
        />
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_weight="1"
        android:orientation="horizontal">
    <Button
        android:id="@+id/button_4"
        android:layout_width="140dp"
        android:layout_height="60dp"
        android:text="ONE"
        />
    <Button
        android:id="@+id/button_5"
        android:layout_width="120dp"
        android:layout_height="60dp"
        android:text="TWO"
        />
    <Button
        android:id="@+id/button_6"
        android:layout_width="150dp"
        android:layout_height="60dp"
        android:text="THREE"
        />
    </LinearLayout>
</LinearLayout>
```
    - mainActivity代码：
```Java
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```
- 实现界面截图：

![线性布局实现过程](https://note.youdao.com/yws/api/personal/file/B91F53651792426F96F67B1C513FB2F2?method=download&shareKey=c501a864423da7dd64225f2372daafad)

![线性布局实现结果](https://note.youdao.com/yws/api/personal/file/43C047E081964CCCBC7225658FE7A24B?method=download&shareKey=dd64cef80dbc96103626ece0bbeb8c35)
## ConstraintLayout界面
- 代码如下：
    - XML代码：
```XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@android:color/black"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Relative  Layout  Example !"
        android:textSize="@android:dimen/app_icon_size"
        android:textColor="@android:color/primary_text_dark"
        android:background="@android:color/darker_gray"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:text="RED"
        android:background="@android:color/holo_red_light"
        app:layout_constraintEnd_toStartOf="@+id/button2"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:text="ORANGE"
        android:background="@android:color/holo_orange_dark"
        app:layout_constraintEnd_toStartOf="@+id/button3"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toEndOf="@+id/button"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />

    <Button
        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:text="YELLOW"
        android:background="@android:color/holo_orange_light"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toEndOf="@+id/button2"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />

    <Button
        android:id="@+id/button4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="60dp"
        android:text="GREEN"
        android:background="@android:color/holo_green_light"
        app:layout_constraintEnd_toStartOf="@+id/button6"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button2" />

    <Button
        android:id="@+id/button5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="160dp"
        android:layout_marginTop="60dp"
        android:text="BLUE"
        android:background="@android:color/holo_blue_light"
        app:layout_constraintEnd_toStartOf="@+id/button6"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button2" />

    <Button
        android:id="@+id/button6"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="60dp"
        android:text="INDIGO"
        android:background="@android:color/holo_purple"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toEndOf="@+id/button4"
        app:layout_constraintTop_toBottomOf="@+id/button2" />

    <Button
        android:id="@+id/button7"
        android:layout_width="399dp"
        android:layout_height="46dp"
        android:layout_marginTop="92dp"
        android:text="VIOLET"
        android:background="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button5" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
    - mainActivity代码：
```JAVA
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```
- 实现界面截图：

![Constraint布局实现过程](https://note.youdao.com/yws/api/personal/file/D81F64CAECC5471BBBBB386DBD87AB1C?method=download&shareKey=0b613aec00b456d79dbcadb396c3c920)

![Constraint实现结果](https://note.youdao.com/yws/api/personal/file/C2B32B1F85FF4FC4821A99EA198F9B26?method=download&shareKey=a94a4c088a17f03a1620c69e3240e7be)

## 表格布局
- 代码如下：
    - XML代码：
```XML
 <TableLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:stretchColumns="1"
        android:layout_weight="3">
        <TableRow>
            <TextView
                android:text="Open..."
                android:padding="5dp" />
            <TextView
                android:text="Ctrl-O"
                android:gravity="right"
                android:padding="3dp" />
        </TableRow>
        <TableRow>
            <TextView
                android:text="Save As..."
                android:padding="3dp" />
            <TextView
                android:text="Ctrl-Shift-S"
                android:gravity="right"
                android:padding="3dp" />
        </TableRow>
    </TableLayout>
```
    - mainActivity代码：同上
- 实现界面截图：

![表格布局实现过程](https://note.youdao.com/yws/api/personal/file/1ED4F57117904DF0B8D6A8463DD3346D?method=download&shareKey=13577eaca08e80dc2a39b85e432f7753)

![表格布局实现结果](https://note.youdao.com/yws/api/personal/file/E619B301095A479D849287FB0D0B3694?method=download&shareKey=209b6e57a28f5ec12e4b97b1f702350a)