Add the following dependencies from the below link at the **app** level gradle file
https://developer.android.com/jetpack/androidx/releases/navigation

val nav_version = "2.8.8"

// Jetpack Compose integration
implementation("androidx.navigation:navigation-compose:$nav_version")

// Views/Fragments integration
implementation("androidx.navigation:navigation-fragment:$nav_version")
implementation("androidx.navigation:navigation-ui:$nav_version")

// Feature module support for Fragments
implementation("androidx.navigation:navigation-dynamic-features-fragment:$nav_version")

under **plugin** {
  id("androidx.navigation.safeargs.kotlin")
}

Add the following dependencies in the **project** level gradle file
buildscript {
    repositories {
        google()
    }
    dependencies {
        classpath(libs.androidx.navigation.safe.args.gradle.plugin)
    }
}

**Adding NavGraph**
To add the navigation component, right click on the **app** -> **New** -> **Android Resource File** -> give the **File Name**  as **nav_graph**, select **Resource Type** as **Navigation**.
Now, the **navigation** folder gets created under the **res** folder with **nav_graph.xml** file in it.

**Adding NavHostFragment**
Go to the **actvitiy_main.xml**, switch to design mode. select **Containers** from the list -> **NavHostFragment**. Drag and Drop it. It automatically detects the **nav_graph** file that was created earlier.
Select **nav_graph** and click on **OK**. Click on the **infer constraints** ![image](https://github.com/user-attachments/assets/cee6f2ea-7be3-4eeb-9d80-ac98448c9818)
option once done

Now, we can see the actviity_main.xml screen as below

![image](https://github.com/user-attachments/assets/085f5b23-4939-4446-9a54-df1755292937)

![image](https://github.com/user-attachments/assets/4fb8cd31-4b5c-47fb-a5ca-298b9eb9358a)

Also, the nav_graph page will look like below

![image](https://github.com/user-attachments/assets/fd2f9766-d7c1-4961-b05f-c631fd1b21c6)

Different Fragments in the Navigation Graph are called **Navigation Destinations**
**Adding Navigation Destination**,

![image](https://github.com/user-attachments/assets/09a8b4d3-15cb-4e32-a791-74a01eeffe0b) -> ![image](https://github.com/user-attachments/assets/aa2f3cd9-4a24-43e9-9de5-086e8a044d2a)

Select **Blank Fragment**

![image](https://github.com/user-attachments/assets/d94f7c66-7516-4eaa-8f89-8d4146034eef)

Click on **NEXT**

![image](https://github.com/user-attachments/assets/06c97b22-5289-4f5c-a827-bb172299d5a7)

Click on **Finish**

If we have multiple framents, ![image](https://github.com/user-attachments/assets/f4b35426-a556-4bee-bea5-bf418fe24783) on the top of the fragment indicates that its the home fragment. In case, if we want to change the Home Fragment, We just need to select the fragment and click on the Home icon ![image](https://github.com/user-attachments/assets/6a90285b-d9f7-48bb-be4f-7943924cfd98)

Converting the Frame Layout to Constraint Layout, Adding an EditText and a Button to the xml file

![image](https://github.com/user-attachments/assets/65c9c256-a7da-40fb-9332-0eb484d7dae8)

Adding the DataBinding to the fragment_home.xml and HomeFragment.kt.
Add another fragment named SecondFragment by clicking on ![image](https://github.com/user-attachments/assets/4fa2ac97-7f98-4576-8fbb-be23d1d2dc3f) Add a TextView to the fragment after changing the FrameLayout to ConstraintLayout
Add the DataBinding as we did for the HomeFragment

Now adding the **Navigation Actions**
In the nav_graph.xml, we can see the 2 fragments that were added by us.
We can note that the StartDestination is set as HomeFragment -> ![image](https://github.com/user-attachments/assets/55d81483-acbd-4436-9f8b-8a95be847397)

Now lets add an action to the button so that onClick of the SUBMIT button, we move to the SecondFragment.
Adding the Action. Click on the right edge and drag it to the second fragment 

![image](https://github.com/user-attachments/assets/54621a15-c4e2-4e64-b43f-84d506b447f3)

Now you can see in the attributes that the action is added as follows

![image](https://github.com/user-attachments/assets/303c18e3-7741-4dd2-9015-99ba5e3b81fc)

Now in the text view mode of nav_graph, we can see that the action has been added for the home fragment

![image](https://github.com/user-attachments/assets/a9c28461-6c5c-46ad-b418-5dde9433b017)

Now let's implement the onClickListener event in the HomeFragment.kt

![image](https://github.com/user-attachments/assets/169572f4-5682-41c7-863a-2e4110e7877f)

**Sending data between Destinations**
As we have an EditText defined in the HomeFragment, lets type a string and pass it to SecondFragment using Bundle.
Best practice is to pass the data through ViewModel but the Navigation Component allows us to pass through bundle
For sending the data from HomeFragment,

![image](https://github.com/user-attachments/assets/0d3922d6-b656-4684-91fe-1d9e83ca8ac3)

For receiving the data in SecondFragment,

![image](https://github.com/user-attachments/assets/5c68e6fd-e9be-40b0-86c3-d92d02bc10e1)

**Adding Animations for Actions**
With reference to the below links, we shall pick slide-in-left, slide-in-right, slide-out-left, slide-out-right and add them.

https://stackoverflow.com/questions/5151591/android-left-to-right-slide-animation

https://stackoverflow.com/questions/18147840/slide-right-to-left-android-animations

Go to **app** -> **Android Resource File** -> give a name to the file -> Select the **resource type** as **Animation** -> **OK**.
Now the resource file will be created inside the anim folder under res directory.
Add the details as mentioned below under Animations and run the app

![image](https://github.com/user-attachments/assets/77df4634-e737-435e-af24-4f36f74565cb)

