[![bintray](https://img.shields.io/badge/bintray-recyclerview-brightgreen.svg)](https://bintray.com/hendraanggrian/recyclerview)
[![download](https://api.bintray.com/packages/hendraanggrian/recyclerview/recyclerview-expandable/images/download.svg)](https://bintray.com/hendraanggrian/recyclerview/recyclerview-expandable/_latestVersion)
[![build](https://travis-ci.com/hendraanggrian/recyclerview-expandable.svg)](https://travis-ci.com/hendraanggrian/recyclerview-expandable)
[![license](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

Expandable RecyclerView
=======================
RecyclerView implementation of [traex's ExpandableLayout](https://github.com/traex/ExpandableLayout).

Download
--------
```gradle
repositories {
    google()
    jcenter()
}

dependencies {
    compile "com.hendraanggrian.recyclerview:recyclerview-expandable:$version"
}
```

Usage
-----
![demo][demo]

Create a row of your RecyclerView:
```xml
<com.hendraanggrian.recyclerview.widget.ExpandableItem
    android:id="@+id/row"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:duration="500"
    app:layoutHeader="@layout/view_content"
    app:layoutContent="@layout/view_header"/>
```

Create your adapter, which must extend `ExpandableRecyclerView.Adapter`:
```java
public class MyAdapter extends ExpandableRecyclerView.Adapter<MyAdapter.ViewHolder> {

    public MyAdapter(LinearLayoutManager layout) {
        super(layout);
        ...
    }

    @Override
    public void onBindViewHolder(MyAdapter.ViewHolder holder, final int position) {
        super.onBindViewHolder(holder, position);
        ...
    }

    public static class ViewHolder extends RecyclerView.ViewHolder {
        ...
    }
}
```

Have an `ExpandableRecyclerView` somewhere in your app, regular `RecyclerView` works too.
```xml
<com.hendraanggrian.recyclerview.widget.ExpandableRecyclerView
    android:id="@+id/recyclerView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```

Then pass LinearLayoutManager to the adapter:
```java
LinearLayoutManager layout = new LinearLayoutManager(this);
RecyclerView.Adapter adapter = new MyAdapter(layout);

recyclerView.setLayoutManager(layout);
recyclerView.setAdapter(adapter);
```

License
-------
    Copyright 2016 Hendra Anggrian

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

[demo]: /art/demo.gif
