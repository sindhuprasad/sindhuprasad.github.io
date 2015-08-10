---
layout: post
title: String vs StringBuilder
---

Sample 1

```Java
String result = "";
for (int i=0;i<1000;i++) {
    result = result + "hello";
}
```

Sample 2

```Java
StringBuilder sb = new StringBuilder();
for (int i=0;i<1000;i++) {
    sb.append("hello");
}
```

In the above code, sample 1 runs faster or the sample 2 ? Or, are they same?

The sample 2 is actually much faster than sample 1. And also more memory efficient too.  Here is why. In sample 1, for each iteration of loop a new `String` object is constructed with the concatenated result. This is essentially a a `O(n^2)` operation. In case of `StringBuilder`, the string "hello" is appended to the same `StringBuilder` object. Therefore its much faster and a `O(1)` operation. However, there is an overhead invovled in growing the capacity of internal character buffer as the string content increases in length.
