### Branch Key

{% section explanation %}
Now you need to add the Branch Key that you received on the Dashboard into your app.
{% endsection %}

{% if page.ios %}

[TODO] Updated screenshots when we have the next version.

Your app key can be retrieved on the [Settings](https://dashboard.branch.io/#/settings) page of the dashboard. Now you need to add it to YourProject-Info.plist (Info.plist for Swift).

1. In plist file, mouse hover "Information Property List" which is the root item under the Key column.
1. After about half a second, you will see a "+" sign appear. Click it.
1. In the newly added row, fill in [TODO] "bnc_app_key" for its key, leave type as String, and enter your app key obtained in above steps in its value column.
1. Save the plist file.

#### Screenshot
![Setting Key in PList Demo](https://s3-us-west-1.amazonaws.com/branch-guides/10_plist.png)

#### Animated Gif
![Setting Key in PList Demo](https://s3-us-west-1.amazonaws.com/branch-guides/9_plist.gif)

{% endif %}
<!---       /iOS-specific Branch Key -->


{% if page.android %}

Your app key can be retrieved on the [Settings](https://dashboard.branch.io/#/settings) page of the dashboard. Now you need to add it to your project workspace. 

1. Navigate to to res/values/strings.xml
2. Add a new resource, with the name "bnc_app_key". Here's what it should look like:

~~~java
<resources>
    <!-- Other existing resources -->

    <!--Change "your app key" to your app key -->
    <string name="bnc_app_key">"your app key"</string>
</resources>
~~~

3. Navigate to AndroidManifest.xml and add the following `<meta-data` tag:

~~~java
<application>
    <!-- Other existing entries -->

    <!-- Add this meta-data below; DO NOT changing the android:value -->
    <meta-data android:name="io.branch.sdk.ApplicationId" android:value="@string/bnc_app_key" />
</application>
~~~


{% endif %}
<!---       /Android-specific Branch Key -->