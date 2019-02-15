---
layout: page
title: AbstractActivity
permalink: /document/app/abstractActivity
menu: false
---

## AbstractActivity

The abstractActivity is subClass from the appCompatActivity.

For use The abstractActivity must be extend activity from this.
```java
public class MainActivity extends AbstractActivity
```

### getActivity
Return current instance from this activity

```java
getActivity();
```

### startActivity
Show other activity with intent

    argument:
        Class class

```java
startActivity(NextActivity.class);}
```

### getVisibleFragment()
Return current fragment (if exist fragment)

```java
getVisibleFragment();
```

### getFragmentList
Return list of fragment in backstack

```java
getFragmentList();
```

### findFragment
Find the fragment from backstack

    argument:
        String tagId

```java
findFragment("tagIdFragment");
```

### hasBackStack
Check any fragment is exist in backstack

```java
if (!hasBackStack()) {
    ....
}
```

### clearBackStack
Clear any fragment from backstack

```java
clearBackStack();
```

### presentFragment
Show fragment instance in activity

    argument:
        AbstractFragment fragment
        int container
        String tagId
        boolean addToBackStack

```java
ExampleFragment exampleFragment = new ExampleFragment();
presentFragment(exampleFragment, R.id.frameLayout, "FRAGMENT_TAG_ID", true);
```