DHCOnDealloc
============

A simple category that allows you set a block to fire when an object is dealloced.

**N.B:** fires *After* object has been released! (possible to do.. make it fire before)

## Instalation

###CocoaPods (preferred)

```ruby
pod "DHCOnDealloc", "~>0.1"
```
  
###Manual
copy contents of `DHCOnDealloc` to your project

##Usage

to setup a block to execute before an object Foo is deallocated:

```objective-c  
#import "NSObject+DHCOnDealloc.h"  

...

Foo *myFoo=[[Foo alloc] init];
[myFoo onDealloc:^{
  NSLog(@"I'll miss you bro");
  //and other more useful stuff
  //be careful of retain cycles
  //(google them)
}];
  myFoo=nil; //ARC will call -dealloc //this will fire your block //he will miss you bro

```
