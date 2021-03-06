# Stfalcon-PriceRangeBar
![](https://i.imgur.com/Ztu6kKp.gif)

# Demo Application
<a href="https://play.google.com/store/apps/details?id=com.stfalcon.stfalconrangebarchart_example" rel="nofollow"><img src="https://camo.githubusercontent.com/0a801b51f6ca951ae0c7dabf4368bf6a4d8c130f/68747470733a2f2f706c61792e676f6f676c652e636f6d2f696e746c2f656e5f75732f6261646765732f696d616765732f62616467655f6e65772e706e67" alt="Get it on Google Play" data-canonical-src="https://play.google.com/intl/en_us/badges/images/badge_new.png" style="max-width:100%;"></a>

## Who we are
Need iOS and Android apps, MVP development or prototyping? Contact us via info@stfalcon.com. We develop software since 2009, and we're known experts in this field. Check out our portfolio and see more libraries from stfalcon-studio.
## Download
Download via Gradle: 
```implementation 'com.github.stfalcon:StfalconPriceRangeBar:0.1.0'```
## Usage
For adding default seekbar with chart just put this code into your layout:
```
<com.stfalcon.pricerangebar.SeekBarWithChart
   android:layout_width="match_parent"
   android:layout_height="wrap_content"/>
```
Or you can use default rangebar with chart just put this code into your layout:
```
<com.stfalcon.pricerangebar.RangeBarWithChart
   android:layout_width="match_parent"
   android:layout_height="wrap_content"/>
```
After that you should to add list entries with data to displaying

```
val barEntrys = ArrayList<BarEntry>()

seekBarEntries.add(BarEntry(30.0f, 5.0f))
seekBarEntries.add(BarEntry(32.0f, 7.0f))
seekBarEntries.add(BarEntry(34.0f, 10.0f))
seekBarEntries.add(BarEntry(36.0f, 11.0f))
seekBarEntries.add(BarEntry(38.0f, 14.0f))
seekBarEntries.add(BarEntry(40.0f, 15.0f))

seekBar.setEntries(barEntrys)
```
You can use many attributes for more flexibility and convenience of use. Here's the full list:
- barActiveLineColor - color of selected part of rangebar/seekbar
- barLineColor - color of unselected part of rangebar/seekbar
- barThumbColor - color of thumb
- barActiveThumbColor - color of active radius in thumb
- barActiveTickRadius - clicked size of thumb
- barChartSelectedBackgroundColor - background color of selected part of chart
- barChartSelectedLineColor - color of selected part of top line in chart
- barChartUnSelectedLineColor - color of unelected part of top line in chart
- barChartUnselectedBackgroundColor - background color of unelected part of chart

For example:
```
<com.stfalcon.pricerangebar.SeekBarWithChart
    android:id="@+id/seekBar"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:barActiveLineColor="@android:color/holo_orange_dark"
    app:barActiveThumbColor="@android:color/holo_blue_light"
    app:barActiveTickRadius="@dimen/custom_active_tick_radius"
    app:barChartSelectedBackgroundColor="@android:color/holo_red_dark"
    app:barChartSelectedLineColor="@android:color/holo_green_dark"
    app:barChartUnSelectedLineColor="@android:color/holo_green_light"
    app:barChartUnselectedBackgroundColor="@android:color/holo_red_light"
    app:barLineColor="@android:color/holo_blue_light"/>
```
If you want to observe any changes in seekbar you should to add callbacks like:
- ```onPinPositionChanged```
- ```onSelectedEntriesSizeChanged```
- ```onSelectedItemsSizeChanged```

If you want to observe any changes in rangebar you should to add callbacks like:
- ```onRangeChanged```
- ```onLeftPinChanged```
- ```onRightPinChanged```
- ```onSelectedEntriesSizeChanged```
- ```onSelectedItemsSizeChanged```

Let's take look a small sample for seekbar:
```
seekBar.onPinPositionChanged = { index, pinValue ->
    println("$pinValue $index")
}
seekBar.onSelectedEntriesSizeChanged = { selectedEntriesSize ->
    println("$selectedEntriesSize column was selected")
}
seekBar.onSelectedItemsSizeChanged = { selectedItemsSize ->
    println("selectedItemsSize elements was selected")
}
```
And for rangebar:
```
rangeBar.onRangeChanged = { leftPinValue, rightPinValue ->
    println("$leftPinValue $rightPinValue")
}
rangeBar.onLeftPinChanged = { index, leftPinValue ->
    println("$index $leftPinValue")
}
rangeBar.onRightPinChanged = { index, rightPinValue ->
    println("$index $rightPinValue")
}
rangeBar.onSelectedEntriesSizeChanged = { selectedEntriesSize ->
    println("$selectedEntriesSize column was selected")
}
rangeBar.onSelectedItemsSizeChanged = { selectedItemsSize ->
    println("$selectedItemsSize elements was selected")
}
```
## License
```
Copyright 2018 stfalcon.com

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
