---
layout: post
title: Testing Asynchronous Code Continued
published: true
date: 2018-03-01 1:00
category: original
tags: code
excerpt_separator: <!--more-->
---

This past week John Sundell wrote a blog post ([Unit testing asynchronous Swift code](https://www.swiftbysundell.com/posts/unit-testing-asynchronous-swift-code)) about unit testing asynchronous code.

As I was trying to apply some fo the techniques when I came across a method I couldn’t mock because I was getting an error.

> Objective-C method `addNotificationRequest:withCompletionHandler:` provided by method `add(_:withCompletionHandler:)` does not match the requirement’s selector (`add:withCompletionHandler:`)  

Consider the following method for `UNUserNotificationCenter` in Swift.

```swift
func add(_ request: UNNotificationRequest, withCompletionHandler completionHandler: ((Error?) -> Swift.Void)? = nil)
```

If you would want to create a Swift protocol to mimic the interface to `UNUserNotificationCenter` that would be pretty simple.

```swift
@objc
protocol UserNotificationCenter {
	func add(_ request: UNNotificationRequest, withCompletionHandler completionHandler: ((Error?) -> Swift.Void)?)
}
```

The problem is that the method signature in Swift is different from the method signature in Objective-C. Here is the method definition in Objective-C.

```swift
- (void)addNotificationRequest:(UNNotificationRequest *)request withCompletionHandler:(nullable void(^)(NSError *__nullable error))completionHandler;
```

Since the Objective-C method has a different method signature than the Swift version, we have to specify the Objective-C method signature in our protocol.

```swift
@objc(addNotificationRequest:withCompletionHandler:)
func add(_ request: UNNotificationRequest, withCompletionHandler completionHandler: ((Error?) -> Swift.Void)?)
```

Now we can implement that method in our mock object!