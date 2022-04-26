# workshop2
## TITLE: 
To display output for arithmetic operations using android studio.

## PROCEDURE:
Step-1:Use Android StudioIDE to create an Android application and name it as My 
App under a package com.example.MyApp, with blank Activity. 
Step-2: Modify the default content of res/layout/activity_main.xml file to display the required content and design the layout.
Step-3: Don’t make any changes to MainActivity.java
Step-4: Run the code and launch the emulator to display the content in Android.

## PROGRAM:
### Mainactivity.java:
```java
package com.example.workshop2;
import android.content.Intent;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 Button send_button;
 EditText send_text;
 @Override
 protected void onCreate(Bundle savedInstanceState)
 {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 send_button = (Button)findViewById(R.id.send_button_id);
 send_text = (EditText)findViewById(R.id.send_text_id);
 send_button.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v)
 {
 String str = send_text.getText().toString();
 Intent intent = new Intent(getApplicationContext(), 
Second_Activity.class);
 intent.putExtra("message_key", str);
 // start the Intent
 startActivity(intent);
 }
 });

```

### Activity_main.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <EditText
 android:id="@+id/send_text_id"
 android:layout_width="300dp"
 android:layout_height="wrap_content"
 android:textSize="25dp"
 android:hint="@string/input"
 android:textStyle="bold"
 android:layout_marginTop="20dp"
 android:layout_marginLeft="40dp"
 tools:ignore="Autofill,SpUsage,TextFields" />
 <Button
 android:id="@+id/send_button_id"
 android:layout_width="wrap_content"
 android:layout_height="40dp"
 android:text="@string/send"
 android:textStyle="bold"
 android:layout_marginTop="150dp"
 android:layout_marginLeft="150dp"/>
</RelativeLayout>
```

### Second_Activity.java:
```
package com.example.workshop2;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
public class Second_Activity extends AppCompatActivity {
 TextView receiver_msg;
 @Override
 protected void onCreate(Bundle savedInstanceState)
 {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_second);
 receiver_msg = (TextView)findViewById(R.id.received_value_id);
 Intent intent = getIntent();
 String str = intent.getStringExtra("message_key");
 receiver_msg.setText(str);
 }
}
```

### Activity_second.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".Second_Activity">
 <TextView
 android:id="@+id/received_value_id"
 android:layout_width="300dp"
 android:layout_height="50dp"
 android:textStyle="bold"
 android:textSize="40dp"
 android:layout_marginTop="20dp"
 android:layout_marginLeft="40dp"/>
</RelativeLayout>
```
OUTPUT:
 ![image](https://user-images.githubusercontent.com/75235334/165352020-bc96fcd0-83e7-4223-aac8-6fbd382bb6aa.png)
![image](https://user-images.githubusercontent.com/75235334/165352070-3ca792e1-8e05-4acd-aa0f-12f3697ccb30.png)

