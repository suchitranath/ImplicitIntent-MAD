# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Suchitra Nath
Registeration Number : 212223220112
*/
```
## activity_main.xml
```

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="24dp">

    <EditText
        android:id="@+id/urlText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter website URL"
        android:inputType="textUri"
        android:text="www.gmail.com" />

    <Button
        android:id="@+id/navigateButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Navigate" />

    <Button
        android:id="@+id/implicitButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Implicit Intent" />

</LinearLayout>

```
## MainActivity.java
```

package com.example.implicitintent;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText urlText;
    Button navigateButton, implicitButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        urlText = findViewById(R.id.urlText);
        navigateButton = findViewById(R.id.navigateButton);
        implicitButton = findViewById(R.id.implicitButton);

        // Navigate button
        navigateButton.setOnClickListener(v -> {
            String url = urlText.getText().toString().trim();

            if (url.isEmpty()) {
                Toast.makeText(this,
                        "Please enter a website URL",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            if (!url.startsWith("http://")
                    && !url.startsWith("https://")) {
                url = "https://" + url;
            }

            Intent intent = new Intent(
                    Intent.ACTION_VIEW,
                    Uri.parse(url)
            );

            startActivity(intent);
        });

        // Implicit Intent button
        implicitButton.setOnClickListener(v -> {
            Uri webpage = Uri.parse("https://www.gmail.com");

            Intent intent = new Intent(
                    Intent.ACTION_VIEW,
                    webpage
            );

            startActivity(intent);
        });
    }
}

```


## OUTPUT
<img width="427" height="862" alt="image" src="https://github.com/user-attachments/assets/192f67bf-5f5a-4eeb-aad7-d34cdbdd9528" />

<img width="392" height="887" alt="image" src="https://github.com/user-attachments/assets/b7f74823-6051-4701-ba6f-22590e84c330" />



## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


