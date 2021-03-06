# Customizable Timeline View for Android
Customizable Timeline View for Android, Create a simple timeline list with few lines of code. You can adjust the image, image size, line color, line size, background to the image and the background size.

![](Screenshot.png)

# Download
Add it in your root `build.gradle` at the end of repositories:

``` groovy
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```
Add the dependency:

``` groovy
dependencies {
    compile 'com.github.qapqap:TimelineView:v1.5'
}
```

# Usage

In your activity java class:
``` java
//create Timeline rows List
ArrayList<TimelineRow> TimelineRowsList = new ArrayList<>();

//create new timeline row (Id, Row Date, Row Title, Row Description)
TimelineRow myRow = new TimelineRow(1, new Date(), "Title", "Description");

//to set the row bitmap image (optional)
myRow.setImage(BitmapFactory.decodeResource(getResources(), R.drawable.img_0));
//to set row Below Line Color (optional)
myRow.setBellowLineColor(Color.argb(255, 255, 255, 255));
//to set row Below Line Size in dp (optional)
myRow.setBellowLineSize(25); 
//to set row Image Size in dp (optional)
myRow.setImageSize(25);
//to set background color of the row image (optional)
myRow.setBackgroundColor(Color.argb(255, 0, 0, 0));
//to set the Background Size of the row image in dp (optional)
myRow.setBackgroundSize(30); 

//add the new row to the list
TimelineRowsList.add(myRow);

//create the Timeline Adapter
ArrayAdapter<TimelineRow> myAdapter = new TimelineViewAdapter(this, 0, TimelineRowsList,
//if true, list will be sorted by date
	true);

//Get the ListView and Bind it with the Timeline Adapter
ListView myListView = (ListView) findViewById(R.id.timelineListView);
myListView.setAdapter(myAdapter);
```

In your activity layout xml
``` xml
<ListView
    android:id="@+id/timelineListView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:divider="@null"
    android:dividerHeight="0dp" />
```

License
--------

    Copyright 2016 Abdullah Alsulaiman.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
