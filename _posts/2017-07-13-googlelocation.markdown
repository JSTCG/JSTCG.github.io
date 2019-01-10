---
layout: post
title: Google查询地理信息API
date: 2017-07-13 19:24:09.000000000 +09:00
tags: Get
---
向Google Map查询给定经纬度的位置信息，返回为JSON

```swift
+ (NSString *)googleReverseStringWithCoordinate:(CLLocationCoordinate2D)coordinate {
    return [NSString stringWithFormat:@"http://maps.google.com/maps/geo?q=%lf,%lf&output=json&sensor=false&accuracy=4", coordinate.latitude,coordinate.longitude];
}
```
