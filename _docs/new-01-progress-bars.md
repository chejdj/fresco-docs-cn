---
docid: progress-bars
title: 进度条
layout: docs
permalink: /docs/progress-bars.html
prev: rounded-corners-and-circles.html
next: scaletypes.html
---

要显示进度条，最简单的办法就是在构建 [hierarchy](using-simpledraweeview.html) 时使用 [ProgressBarDrawable](../javadoc/reference/com/facebook/drawee/drawable/ProgressBarDrawable.html) 类，如下所示：

```java
.setProgressBarImage(new ProgressBarDrawable())
```

这样，在 Drawee 的底部就会有一个深蓝色的矩形进度条。

### 自定义进度条

如果你想自定义进度条，请注意，如果想精确显示加载进度，需要重写 [Drawable.onLevelChange](http://developer.android.com/reference/android/graphics/drawable/Drawable.html#onLevelChange\(int\))：

```java
class CustomProgressBar extends Drawable {
   @Override
   protected boolean onLevelChange(int level) {
     // level is on a scale of 0-10,000
     // where 10,000 means fully downloaded

     // your app's logic to change the drawable's
     // appearance here based on progress
   }
}
```

### 示例

Fresco 示例应用中的 [DraweeHierarchyFragment](https://github.com/facebook/fresco/blob/master/samples/showcase/src/main/java/com/facebook/fresco/samples/showcase/drawee/DraweeHierarchyFragment.java) 类演示了使用带有进度条的 Drawable 的使用。

<video controls="" autoplay="">
  <source src="/static/videos/01-progress-bars.mp4" type="video/mp4">
</video>