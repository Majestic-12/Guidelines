Continuous Integration for iOS Apps
============

This guide will help you set up automated UI Test Unit, Code Coverage, MDM and Continuous Integration for your iOS project. 

It will help you set up all needed build tools. 

-------
<p align="center">
<a href="#installation">Installation</a> &bull; 
<a href="#setting-up-fastlane">Setting up</a> &bull; 
<a href="#example-project">Example Project</a> &bull; 
<a href="#Apple-Guidelines">Apple Guidelines</a> &bull; 
<a href="#Apple-Coding-Style">Apple Coding Style</a> &bull; 
<a href="#help">Help</a>
</p>
-------

## Installation

Requirements:

- OS X 10.11 (El Capitan) or newer
- OS X Server 5 or newer
- Xcode 7.1

Additionally, to an Xcode installation, you also need the Xcode command line tools set up

xcode-select --install


## Setting up `UI Test Unit`

Before changing anything, I recommend committing everything in `git` (in case something goes wrong).

When running the setup commands, please read the instructions shown in the terminal. There is usually a reason they are there.

`XCode` will create all necessary files and folders for you with the following command.

1. Install OS X 10.11.
1. Install OS X Server 5.
1. Install XCode 7.1 and above.
1. Create a new target as `iOS UI Testing Bundle` in XCode.

1. If you haven't already used [`snapshot`](https://github.com/KrauseFx/snapshot), confirm with `y` if you want your screenshots to be created automatically.
1. If you want to [`sigh`](https://github.com/KrauseFx/sigh) to download, renew or create your provisioning profiles, confirm with `y`.

That's it, you should have received a success message. 


# Apple Guidelines

[Designing for Real-World Networks](https://developer.apple.com/library/ios/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/WhyNetworkingIsHard/WhyNetworkingIsHard.html).

[iOS Human Interface Guidelines](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/index.html#//apple_ref/doc/uid/TP40006556).

[Apple Secure Coding Guide](https://developer.apple.com/library/ios/documentation/Security/Conceptual/SecureCodingGuide/Introduction.html#//apple_ref/doc/uid/TP40002415).




# Apple Coding Style

**Clarity**

###### It is good to be both clear and brief as possible, but clarity shouldn’t suffer because of brevity:

Code | Commentary
------------ |-----
insertObject:atIndex: | Good.
insert:at: | Not clear; what is being inserted? what does “at” signify?
removeObjectAtIndex: | Good.
removeObject: | Good, because it removes object referred to in argument.
remove: | Not clear; what is being removed?


In general, don’t abbreviate names of things. Spell them out, even if they’re long:

Code | Commentary
------------ |-----
destinationSelection | Good.
destSel | Not clear.
setBackgroundColor: | Good.
setBkgdColor: | Not clear.
remove: | Not clear; what is being removed?


You may think an abbreviation is well-known, but it might not be, especially if the developer encountering your method or function name has a different cultural and linguistic background.

However, a handful of abbreviations are truly common and have a long history of use. You can continue to use them; see Acceptable Abbreviations and Acronyms.

Avoid ambiguity in API names, such as method names that could be interpreted in more than one way.

Code | Commentary
------------ |-----
sendPort | Does it send the port or return it?
displayName | Does it display a name or return the receiver’s title in the user interface?


**Consistency**

Try to use names consistently throughout the Cocoa programmatic interfaces. 

If you are unsure, browse the current header files or reference documentation for precedents.

Consistency is especially important when you have a class whose methods should take advantage of polymorphism. 

Methods that do the same thing in different classes should have the same name.


Code | Commentary
------------ |-----
- (NSInteger)tag | Defined in NSView, NSCell, NSControl.
- (void)setStringValue:(NSString *)| Defined in a number of Cocoa 

See also Method Arguments.

**No Self Reference**

- Names shouldn’t be self-referential.

Code | Commentary
------------ |-----
NSString | Okay.
NSStringObject | Self-referential.


- Constants that are masks (and thus can be combined in bitwise operations) are an exception to this rule, as are constants for notification names.


Code | Commentary
------------ |-----
NSUnderlineByWordMask | Okay.
NSTableViewColumnDidMoveNotification | Okay.


# sudo gem install snapshot

```
snapshot
```

## sudo gem install snapshot

To skip cleaning the project:
```
snapshot --noclean
```


### sudo gem install snapshot
```objective-c
#ifdef SNAPSHOT
// Your Code here
#endif
```

sudo gem install snapshot

    sudo gem install snapshot