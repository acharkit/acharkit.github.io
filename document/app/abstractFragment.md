---
layout: page
title: AbstractFragment
permalink: /document/app/abstractFragment
menu: false
---

## AbstractFragment

The abstractFragment is subClass from the fragment.

For use The abstractFragment must be extend fragment from this.

```java
public class MainFragment extends AbstractFragment
```

***

#### getTagId
Return fragment identifier

```java
getTagId();
```

***

#### setTagId
Set identifier for fragment

    argument:
        String tagId

```java
fragment.setTagId("exampleTagId");
```

***

#### fragmentManager
Return instance of fragmentManager to do transactions

Note: To use, the activity must inherit from [the abstractActivity](/document/app/abstractActivity)

```java
FragmentTransaction transaction = fragmentManager().beginTransaction();
```

***

#### actionFragment
ActionFragment has the function to change the fragment

    argument:
        int frameLayoutId
        int type
        boolean addToBackStack

```java
fragment.actionFragment(R.id.frameLayout, AbstractFragment.TYPE_REPLACE, true);
```

***

#### removeFragmentPopBackStack
Remove the fragment from backstack

```java
fragment.removeFragmentPopBackStack();
```

***

#### setInstantiate
Find instance of this fragment in backstack

If pass 'true' use exist fragment in backstack

Else pass 'false' use new instance

    argument:
        boolean instantiate

```java
fragment.setInstantiate(true);
```