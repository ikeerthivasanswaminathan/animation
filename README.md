# Ex.No: 6 - Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.

## AIM:
To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Design the layout using activity_main.xml

Step 3: Add an ImageView to display the image and add buttons for each animation (Move, Blink, Fade, Clockwise, Zoom, Slide).

Step 4: Import the image into the drawable folder.

Step 5: Create animation XML files under res/anim/ for each animation type such as blink, fade, move, rotate, slide and zoom.

Step 6: Type the Java program in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

### Program to display animation operation”.

Developed by : KEERTHIVASAN S

Registeration Number : 212223220046

### drawable - seclogo.png

<img width="7384" height="1597" alt="seclogo" src="https://github.com/user-attachments/assets/a73493ff-088a-4df9-9f0a-88ebfb5fd67c" />

### activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageview"
        android:layout_width="300dp"
        android:layout_height="400dp"
        android:src="@drawable/seclogo"
        android:contentDescription="Animation Image"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="50dp" />

    <Button
        android:id="@+id/blink"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Blink"
        app:layout_constraintTop_toBottomOf="@id/imageview"
        app:layout_constraintStart_toStartOf="parent"
        android:layout_marginTop="30dp" />

    <Button
        android:id="@+id/rotate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Rotate"
        app:layout_constraintTop_toBottomOf="@id/imageview"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="30dp" />

    <Button
        android:id="@+id/fade"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Fade"
        app:layout_constraintTop_toBottomOf="@id/blink"
        app:layout_constraintStart_toStartOf="parent"
        android:layout_marginTop="15dp" />

    <Button
        android:id="@+id/move"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Move"
        app:layout_constraintTop_toBottomOf="@id/rotate"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="15dp" />

    <Button
        android:id="@+id/slide"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Slide"
        app:layout_constraintTop_toBottomOf="@id/fade"
        app:layout_constraintStart_toStartOf="parent"
        android:layout_marginTop="15dp" />

    <Button
        android:id="@+id/zoom"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Zoom"
        app:layout_constraintTop_toBottomOf="@id/move"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="15dp" />

    <Button
        android:id="@+id/stop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Stop Animation"
        app:layout_constraintTop_toBottomOf="@id/slide"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="20dp" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### blink.xml

```
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:duration="500"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />
```

### rotate.xml

```
<?xml version="1.0" encoding="utf-8"?>
<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatCount="infinite" />
```

### fade.xml

```
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="2000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />
```

### move.xml

```
<?xml version="1.0" encoding="utf-8"?>
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="2000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />
```

### zoom.xml

```
<?xml version="1.0" encoding="utf-8"?>
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="1.5"
    android:fromYScale="1.0"
    android:toYScale="1.5"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatMode="reverse"
    android:repeatCount="infinite" />
```

### slide.xml

```
<?xml version="1.0" encoding="utf-8"?>

<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0%"
    android:toXDelta="100%"
    android:duration="1000" />
```

### MainActivity.java

```
package com.example.animation;

import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {
    private ImageView imageView;
    private Button blink, rotate, fade, move, slide, zoom, stop;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageview);
        blink = findViewById(R.id.blink);
        rotate = findViewById(R.id.rotate);
        fade = findViewById(R.id.fade);
        move = findViewById(R.id.move);
        slide = findViewById(R.id.slide);
        zoom = findViewById(R.id.zoom);
        stop = findViewById(R.id.stop);

        createAnimation(blink, R.anim.blink);
        createAnimation(rotate, R.anim.rotate);
        createAnimation(fade, R.anim.fade);
        createAnimation(move, R.anim.move);
        createAnimation(slide, R.anim.slide);
        createAnimation(zoom, R.anim.zoom);
        stop.setOnClickListener(v -> imageView.clearAnimation());
    }
    private void createAnimation(View view, int animResId) {
        view.setOnClickListener(v -> {
            // Load the animation from the specified resource ID
            Animation animation = AnimationUtils.loadAnimation(MainActivity.this, animResId);
            // Start the animation on the ImageView
            imageView.startAnimation(animation);
        });
    }
}
```

## OUTPUT

### Default Page

<img width="1919" height="1079" alt="exp6op1" src="https://github.com/user-attachments/assets/ce4a40a3-6734-4a7b-b415-1a8e4d030086" />

### Blink Function

<img width="1919" height="1079" alt="exp6op2" src="https://github.com/user-attachments/assets/7579a0e4-0827-4513-90aa-22a3f0729d43" />

### Fade Function

<img width="1919" height="1079" alt="exp6op3" src="https://github.com/user-attachments/assets/59a43cad-8f41-43d9-b012-e8f9659280ca" />

### Slide Function

<img width="1919" height="1079" alt="exp6op4" src="https://github.com/user-attachments/assets/fc7abdca-385a-4f22-8414-390a195250ec" />

### Rotate Function

<img width="1919" height="1079" alt="exp6op5" src="https://github.com/user-attachments/assets/7d7f58b2-c11e-46fc-81a3-a0e39b17c3f3" />

### Move Function

<img width="1919" height="1079" alt="exp6op6" src="https://github.com/user-attachments/assets/8bf4ffb1-c0a5-4a17-8cff-758fb8bd056a" />

### Zoom Function

<img width="1919" height="1079" alt="exp6op7" src="https://github.com/user-attachments/assets/9a87dd54-22dc-44e0-a32e-80cf480fc87b" />

### Stop Animation Function

<img width="1919" height="1079" alt="exp6op8" src="https://github.com/user-attachments/assets/00b973d5-93e7-45c4-a2a3-e4263a0d99fb" />

## RESULT
Thus, the implementation of Animation application using android studio executed successfully.
