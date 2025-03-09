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

Adding NavHostFragment,

![image](https://github.com/user-attachments/assets/09a8b4d3-15cb-4e32-a791-74a01eeffe0b) -> ![image](https://github.com/user-attachments/assets/aa2f3cd9-4a24-43e9-9de5-086e8a044d2a)

Select **Blank Fragment**

![image](https://github.com/user-attachments/assets/d94f7c66-7516-4eaa-8f89-8d4146034eef)

Click on **NEXT**

![image](https://github.com/user-attachments/assets/06c97b22-5289-4f5c-a827-bb172299d5a7)

Click on **Finish**

IF we have multiple framents, ![image](https://github.com/user-attachments/assets/f4b35426-a556-4bee-bea5-bf418fe24783) on the top of the fragment indicates that its the home fragment. In case, if we want to change the Home Fragment, We just need to select the fragment and click on the Home icon ![image](https://github.com/user-attachments/assets/6a90285b-d9f7-48bb-be4f-7943924cfd98)







