# TabLayout
Implementing TabLayout &amp; ViewPager using Java

## Creating fragments, viewpager, and tablayout.


Defining two or three empty fragments:

```
// Defining a view in my first tab
public class FirstFragment extends Fragment {

    @Override
    public View onCreateView(
            LayoutInflater inflater, ViewGroup container,
            Bundle savedInstanceState
    ) {
        // Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_first, container, false);
    }

    public void onViewCreated(@NonNull View view, Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);

    }
}
```

Defining viewpager and tablayout in .xml file (separate or together):

```
    <androidx.viewpager.widget.ViewPager
    android:id="@+id/mainViewPager"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    />
    ...
    ...
    ...
    <com.google.android.material.tabs.TabLayout
    android:id="@+id/mainTabLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:tabBackground="@color/colorPrimary"
    app:tabIndicatorColor="@color/colorLightGrey"
    app:tabTextColor="@color/colorLightGrey"
    app:tabSelectedTextColor="@android:color/white"
    app:tabRippleColor="@color/colorPrimaryDark"
    app:tabTextAppearance="@android:style/TextAppearance.Widget.TabWidget"
    />

```

In my MainActivity must be declared all components such as:

```
    private ViewPager viewPager;
```

Looking the components using findViewById method such as:

```
   viewPager = findViewById(R.id.mainViewPager);
```

Include an inner class in MainActivity:

```
  //**************************************************************
  // INNER CLASS PAGER ADAPTER
  //**************************************************************
    class MyPagerAdapter extends FragmentPagerAdapter
    ...
    ...
```

Finally, I setup viewpager and tabs such as.

```
   myPagerAdapter = new MyPagerAdapter(getSupportFragmentManager(), FragmentPagerAdapter.BEHAVIOR_RESUME_ONLY_CURRENT_FRAGMENT);
   tabLayout.setupWithViewPager(viewPager);
   viewPager.setAdapter(myPagerAdapter);
```

**I can define some specific behavior in each tab (fragment). For example, Tab1 and Tab3 show a FloatingActionButton, but Tab 2 does not show it. See code for details.**

## Final Result:

<p align="center">
<img src="images/01.png" width="250"> <img src="images/02.png" width="250"> 
<img src="images/03.png" width="250">
</p>
