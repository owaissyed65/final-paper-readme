# Measurement Units in Android Development

When developing Android applications, understanding measurement units is crucial for creating responsive and visually consistent UIs across different screen sizes and resolutions. Here’s a breakdown of the most commonly used units:

## 1. **px (Pixels)**
- **Definition**: A pixel is the smallest unit of measurement on the screen. It is an absolute unit that corresponds to a single dot on the screen.
- **Use Case**: Rarely used for UI design, as it doesn’t adapt to different screen densities.
- **Characteristics**:
  - Fixed size and does not scale with screen density.
  - Not recommended for layouts, as it can result in inconsistent UI across devices.

## 2. **dp/dip (Density-independent Pixels)**
- **Definition**: A virtual pixel unit that scales according to the screen's density (dots-per-inch or DPI). It ensures consistent sizing across different screen resolutions.
- **Use Case**: Preferred for defining layout dimensions (e.g., margins, padding, and view sizes).
- **Characteristics**:
  - 1 dp = 1 physical pixel on a 160 dpi screen (baseline density).
  - Scales automatically based on the device's density factor.

## 3. **sp (Scale-independent Pixels)**
- **Definition**: Similar to dp, but also accounts for the user's font size preferences. It is used primarily for text size to ensure readability.
- **Use Case**: Recommended for defining text sizes in the application.
- **Characteristics**:
  - Scales with screen density and user font size settings.
  - Ensures that text remains readable on all devices.

## Summary
| Unit | Scales with Screen Density? | Scales with User Font Settings? | Recommended Use |
|------|-----------------------------|----------------------------------|-----------------|
| px   | No                          | No                               | Rarely used     |
| dp   | Yes                         | No                               | Layout dimensions |
| sp   | Yes                         | Yes                              | Text sizes       |

By using `dp` and `sp` appropriately, you can create a responsive and accessible user interface that works well on a wide range of devices.

# Implicit vs Explicit

In Android, **intents** are used to communicate between components (like activities, services, etc.). They can be of two types:

---

### **1. Implicit Intent**
- **Definition:** Does not specify the target component. Instead, it specifies an action to perform.
- used to communicate with other apps
- **Example Use Case:**
  - Open a webpage.
  - Share text or images.
  - Dial a phone number.
- **Example Code:**
  ```java
  Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://example.com"));
  startActivity(intent);
  ```
- **Key Point:** The system decides the best component to handle the intent.

---

### **2. Explicit Intent**
- **Definition:** Specifies the exact target component (activity, service, etc.) to start.
- used to communicate with other apps
- **Example Use Case:**
  - Navigate between activities in the same app.
- **Example Code:**
  ```java
  Intent intent = new Intent(CurrentActivity.this, TargetActivity.class);
  startActivity(intent);
  ```
- **Key Point:** You explicitly state the component to handle the intent.

---

### Summary Table

| **Feature**        | **Implicit Intent**             | **Explicit Intent**               |
|---------------------|---------------------------------|-----------------------------------|
| **Target**          | System finds suitable component | Specific component is defined.    |
| **Use Case**        | Open external apps or services | Navigate within the app.          |
| **Example Action**  | View a URL, Share, Dial        | Open another activity.            |

# Dimension Value in Android

A **dimension value** is an XML-defined value that is defined in an XML file within the project's `res/values` folder. It is used to define the styling dimensions for different widgets to be included in the Android project. 

Using a `dimens.xml` file is considered good coding practice to better handle dimension changes.

## Steps to Add a Dimension XML File to the Values Folder

1. Right-click on the `values` folder.
2. Select `New > Values Resource File` to open the "New Resource File" dialog window.

## Adding Dimension Values

To define a dimension value, the `<dimen>` tag is used. A dimension value is defined by a number followed by a unit of measurement.

### Measurement Units
- **dp** (density-independent pixels)
- **px** (pixels)
- **sp** (scale-independent pixels)

### Example Usage
```xml
<TextView
    android:padding="@dimen/myVal" />
```
# Arrays in Android

An **array** is a data structure that consists of a collection of elements (values or variables), each of the same memory size, and each identified by at least one array index or key.

## Defining Arrays in Android

Arrays can be defined in the `arrays.xml` file. This file is typically placed in the `res/values` folder of the project.

### Example:

```xml
<resources>
    <string-array name="my_array">
        <item>Value 1</item>
        <item>Value 2</item>
        <item>Value 3</item>
    </string-array>
</resources>
**``**
```

# Style vs Theme
In Android app development, **Themes** and **Styles** are used to define the visual appearance of UI elements. While they are similar, they serve different purposes and scopes.

---

### **1. Style**
- **Definition:** A collection of attributes that specify the appearance of a single UI element.
- **Scope:** Applied to individual views or widgets.
- **Use Case:** Customizing the look of a specific widget or view (e.g., button, text view).
- **Example Code:**
  ```xml
  <!-- styles.xml -->
  <style name="MyButtonStyle">
      <item name="android:background">#FF6200EE</item>
      <item name="android:textColor">#FFFFFF</item>
      <item name="android:padding">10dp</item>
  </style>
  ```
  ```xml
  <!-- activity_main.xml -->
  <Button
      style="@style/MyButtonStyle"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="Click Me"/>
  ```

---

### **2. Theme**
- **Definition:** A collection of styles that apply globally to an entire app or activity, defining the overall look and feel.
- **Scope:** Applied to an activity or the entire application.
- **Use Case:** Setting a consistent appearance for the app, such as colors, fonts, and general design.
- **Example Code:**
  ```xml
  <!-- themes.xml -->
  <style name="AppTheme" parent="Theme.Material3.DayNight.DarkActionBar">
      <item name="colorPrimary">#6200EE</item>
      <item name="colorPrimaryVariant">#3700B3</item>
      <item name="colorOnPrimary">#FFFFFF</item>
  </style>
  ```
  ```xml
  <!-- AndroidManifest.xml -->
  <application
      android:theme="@style/AppTheme">
      ...
  </application>
  ```

---

### **Key Differences**

| **Feature**       | **Style**                                        | **Theme**                                       |
|--------------------|--------------------------------------------------|------------------------------------------------|
| **Scope**          | Specific to a single view or widget.            | Applies to an entire app, activity, or fragment. |
| **Purpose**        | Customizes the appearance of individual elements. | Defines the global appearance of the app.      |
| **Application**    | Applied using the `style` attribute in XML.      | Applied via the `theme` attribute in the manifest or activity. |
| **Inheritance**    | Can inherit from other styles.                   | Can inherit from base themes like `Material3`. |
| **Examples**       | Button, TextView styles.                        | Light/Dark mode, Material Themes.             |

---

### **When to Use:**
- Use **Styles** for customizing individual components.
- Use **Themes** to define a consistent look for your app or activity.

# Animations:
### **Android Animation**
Android animation enhances the user experience by adding motion to UI elements, making the app more interactive and visually appealing. It allows developers to animate views, transitions, or drawable objects.

---

### **Types of Animation in Android**

1. **Property Animation**  
   - **Definition:** Introduced in API level 11 (Android 3.0), it changes the properties of objects, such as position, rotation, scale, and alpha (opacity).
   - **Key Classes:**
     - `ObjectAnimator`
     - `ValueAnimator`
   - **Example:**
     ```java
     ObjectAnimator animation = ObjectAnimator.ofFloat(view, "translationX", 0f, 100f);
     animation.setDuration(1000); // 1 second
     animation.start();
     ```
   - **Use Case:** Smooth transitions like fading, scaling, or movement of views.

---

2. **View Animation (Tween Animation)**  
   - **Definition:** Animates the view properties, such as position, size, rotation, or transparency, without actually changing the view’s properties.
   - **Types:**
     - `TranslateAnimation` (movement)
     - `ScaleAnimation` (scaling)
     - `RotateAnimation` (rotation)
     - `AlphaAnimation` (fading)
   - **Example:**
     ```xml
     <!-- res/anim/translate.xml -->
     <translate
         xmlns:android="http://schemas.android.com/apk/res/android"
         android:fromXDelta="0%"
         android:toXDelta="50%"
         android:duration="1000"/>
     ```
     ```java
     Animation animation = AnimationUtils.loadAnimation(context, R.anim.translate);
     view.startAnimation(animation);
     ```
   - **Use Case:** Simple animations like sliding, fading, or rotating views.

---

3. **Drawable Animation (Frame Animation)**  
   - **Definition:** Plays a sequence of drawable resources like a flipbook.
   - **Example:**
     ```xml
     <!-- res/drawable/frame_animation.xml -->
     <animation-list xmlns:android="http://schemas.android.com/apk/res/android" android:oneshot="false">
         <item android:drawable="@drawable/frame1" android:duration="200"/>
         <item android:drawable="@drawable/frame2" android:duration="200"/>
         <item android:drawable="@drawable/frame3" android:duration="200"/>
     </animation-list>
     ```
     ```java
     ImageView imageView = findViewById(R.id.imageView);
     imageView.setBackgroundResource(R.drawable.frame_animation);
     AnimationDrawable animation = (AnimationDrawable) imageView.getBackground();
     animation.start();
     ```
   - **Use Case:** Animating icons, sprites, or simple visual effects.

---

4. **Motion Layout Animation**  
   - **Definition:** A powerful tool introduced in ConstraintLayout, allowing complex motion and widget animations using `MotionScene`.
   - **Example:**
     ```xml
     <!-- res/xml/motion_scene.xml -->
     <Transition
         app:constraintSetStart="@id/start"
         app:constraintSetEnd="@id/end"
         app:duration="1000">
         <OnSwipe app:dragDirection="dragUp" app:touchAnchorId="@id/view" />
     </Transition>
     ```
   - **Use Case:** Creating complex animations like interactive transitions or gestures.

---

5. **Physics-Based Animation (Dynamic Animation)**  
   - **Definition:** Introduced in API level 16 (Android 4.1), it uses physics principles to create natural animations.
   - **Key Classes:**
     - `SpringAnimation`
     - `FlingAnimation`
   - **Example:**
     ```java
     SpringAnimation spring = new SpringAnimation(view, SpringAnimation.TRANSLATION_Y, 0);
     spring.getSpring().setStiffness(SpringForce.STIFFNESS_LOW);
     spring.start();
     ```
   - **Use Case:** Bouncing effects, overscroll animations.

---

### **Summary Table**

| **Animation Type**       | **Description**                                   | **Use Case**                               |
|---------------------------|-------------------------------------------------|-------------------------------------------|
| **Property Animation**    | Animates object properties like position, scale | Smooth transitions or complex animations. |
| **View Animation**        | Animates view's appearance and behavior         | Simple animations like slide or fade.     |
| **Drawable Animation**    | Plays a sequence of drawable resources          | Sprite animations or icon animations.     |
| **Motion Layout**         | Animates views with gestures and transitions    | Interactive and complex animations.       |
| **Physics-Based Animation** | Adds realistic motion using physics principles | Natural effects like bounce or fling.     |

---

### **Conclusion**
Android offers multiple animation techniques to create interactive and engaging UI experiences. Choose the type based on the complexity and functionality required for your app.

# Lecture 8

# Fragements:
### **What are Fragments in Android App Development?**

A **Fragment** is a modular and reusable portion of a user interface in an Android app. It represents a part of the app's UI or behavior and is embedded within an **Activity**. Fragments allow for more flexible and dynamic UI designs, especially in applications that need to support multiple screen sizes and orientations.

---

### **Key Characteristics of Fragments**
1. **Modular and Reusable:**  
   - Fragments can be reused across multiple activities or within the same activity.
2. **Lifecycle:**  
   - Fragments have their own lifecycle, which is closely tied to the lifecycle of the hosting activity.
3. **Dynamic UI:**  
   - You can add, remove, or replace fragments dynamically during runtime.
4. **Independent Logic:**  
   - Each fragment can have its own logic, UI layout, and event handling.

---

### **Fragment Lifecycle**
The lifecycle of a fragment is similar to an activity but has additional states. The key methods are:

1. **onAttach:** Called when the fragment is attached to an activity.
2. **onCreate:** Initialize the fragment (no UI yet).
3. **onCreateView:** Inflate the fragment's UI.
4. **onActivityCreated:** The activity's `onCreate` method has completed.
5. **onStart:** The fragment becomes visible.
6. **onResume:** The fragment is active and interacting with the user.
7. **onPause:** The fragment is partially visible (e.g., another activity is overlayed).
8. **onStop:** The fragment is no longer visible.
9. **onDestroyView:** The fragment’s UI is destroyed.
10. **onDestroy:** Fragment is cleaned up.
11. **onDetach:** Fragment is detached from the activity.

---

### **Why Use Fragments?**
1. **Dynamic UI Design:**  
   - Allows different layouts for tablets and smartphones by combining or splitting UI components.
2. **Reusability:**  
   - Fragments can be reused across activities, reducing code duplication.
3. **Navigation:**  
   - Facilitates modern navigation patterns, such as swipe views or tab layouts.
4. **Modular Design:**  
   - Helps in separating concerns by dividing UI and logic into smaller, manageable components.

---

### **How to Create and Use Fragments**

1. **Create a Fragment Class:**
   ```java
   public class ExampleFragment extends Fragment {
       @Override
       public View onCreateView(LayoutInflater inflater, ViewGroup container,
                                Bundle savedInstanceState) {
           return inflater.inflate(R.layout.fragment_example, container, false);
       }
   }
   ```

2. **Add a Fragment to an Activity (Static):**
   - In the activity's XML layout:
     ```xml
     <fragment
         android:id="@+id/example_fragment"
         android:name="com.example.ExampleFragment"
         android:layout_width="match_parent"
         android:layout_height="match_parent" />
     ```

3. **Add a Fragment Dynamically (Runtime):**
   ```java
   FragmentManager fragmentManager = getSupportFragmentManager();
   FragmentTransaction transaction = fragmentManager.beginTransaction();

   ExampleFragment fragment = new ExampleFragment();
   transaction.add(R.id.fragment_container, fragment);
   transaction.commit();
   ```

---

### **Communication Between Fragment and Activity**
1. **Using Interfaces:**
   - The fragment can define a callback interface to communicate with its hosting activity.
   ```java
   public interface OnFragmentInteractionListener {
       void onFragmentInteraction(String data);
   }
   ```

2. **Shared ViewModel:**
   - Use the **ViewModel** class for communication between activities and fragments when using MVVM.

---

### **Advantages of Fragments**
- Supports flexible UI for devices with varying screen sizes.
- Encourages modular design for better maintainability and testing.
- Can handle dynamic UI changes at runtime.

---

### **Common Use Cases**
- **Master-Detail Layouts:** For tablets and large screens.
- **Navigation:** Swiping between pages, tab navigation, or bottom navigation.
- **Reusable UI Components:** Shared across different parts of the app.

---

### **Conclusion**
Fragments are a powerful tool in Android app development that provide flexibility, modularity, and better support for dynamic and multi-screen UIs. By properly using fragments, you can create apps that are maintainable, scalable, and adaptive to different devices.

## Types of Fragements:
In Android, **fragments** can be categorized based on their use cases and behavior. Here are the common types of fragments in simple terms:

---

### **1. List Fragment**
- **Definition:** Displays a list of items to the user. It is a subclass of the `Fragment` class specifically designed for lists.
- **Use Case:** Showing lists like contact names, menu options, or a list of products.
- **Example:**  
  ```java
  public class MyListFragment extends ListFragment {
      @Override
      public void onActivityCreated(Bundle savedInstanceState) {
          super.onActivityCreated(savedInstanceState);
          ArrayAdapter<String> adapter = new ArrayAdapter<>(
              getActivity(),
              android.R.layout.simple_list_item_1,
              new String[] { "Item 1", "Item 2", "Item 3" });
          setListAdapter(adapter);
      }
  }
  ```

---

### **2. Dialog Fragment**
- **Definition:** Displays a fragment as a dialog box.
- **Use Case:** Showing pop-ups like alerts, confirmation boxes, or custom input dialogs.
- **Example:**  
  ```java
  public class MyDialogFragment extends DialogFragment {
      @Override
      public Dialog onCreateDialog(Bundle savedInstanceState) {
          return new AlertDialog.Builder(getActivity())
              .setTitle("Dialog Title")
              .setMessage("This is a dialog fragment.")
              .setPositiveButton("OK", (dialog, which) -> dialog.dismiss())
              .create();
      }
  }
  ```

---

### **3. Preference Fragment**
- **Definition:** Used to create a settings screen. It displays preferences that the user can configure.
- **Use Case:** Implementing app settings, like toggles for notifications or themes.
- **Example:**  
  ```java
  public class MyPreferenceFragment extends PreferenceFragment {
      @Override
      public void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          addPreferencesFromResource(R.xml.preferences);
      }
  }
  ```

---

### **4. Master-Detail Fragment**
- **Definition:** Used for displaying two fragments side by side, typically on tablets or large screens. One fragment acts as the "master" (list), and the other as the "detail" (details of the selected item).
- **Use Case:** Email apps where the left pane shows email subjects and the right pane shows the email content.
- **Example:**
  - Master: Shows the list of items.
  - Detail: Displays item details when an item is clicked.

---

### **5. Dynamic Fragment**
- **Definition:** Added, removed, or replaced at runtime using code, rather than being statically defined in XML.
- **Use Case:** Apps where UI needs to change dynamically, like switching between fragments in a `ViewPager` or based on user interaction.
- **Example:**  
  ```java
  FragmentManager manager = getSupportFragmentManager();
  FragmentTransaction transaction = manager.beginTransaction();
  MyFragment fragment = new MyFragment();
  transaction.add(R.id.fragment_container, fragment);
  transaction.commit();
  ```

---

### **6. Static Fragment**
- **Definition:** Defined directly in the XML layout file and remains fixed during the app's lifecycle.
- **Use Case:** Simple layouts where the fragment doesn't need to change dynamically.
- **Example (XML):**
  ```xml
  <fragment
      android:id="@+id/static_fragment"
      android:name="com.example.MyFragment"
      android:layout_width="match_parent"
      android:layout_height="match_parent" />
  ```

---

### **Summary Table**

| **Type of Fragment**      | **Description**                                 | **Use Case**                              |
|---------------------------|-----------------------------------------------|------------------------------------------|
| **List Fragment**          | Displays a list of items.                     | Contact list, menu options.              |
| **Dialog Fragment**        | Displays a fragment as a dialog.              | Alerts, confirmation boxes.              |
| **Preference Fragment**    | Creates a settings screen.                    | App settings like toggles and themes.    |
| **Master-Detail Fragment** | Shows two fragments side by side.             | Email apps, large-screen layouts.        |
| **Dynamic Fragment**       | Added/removed at runtime via code.            | Flexible, interactive UIs.              |
| **Static Fragment**        | Defined in XML and fixed in layout.           | Simple, static layouts.                  |

---

### **Conclusion**
Fragments are versatile and can adapt to various use cases, such as lists, dialogs, or settings. The type of fragment to use depends on your app's design and functionality requirements.

