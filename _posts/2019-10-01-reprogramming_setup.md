---
layout: post
title: Reprogramming LilyTiny - Day 1
---

## Setting up

My students and I are trying to follow the instructions to reprogram the [Lily Tiny](https://www.sparkfun.com/products/10899) microcontroller.
The tutorial that we are using is _[Re-Programming the LilyTiny / LilyTwinkle](https://learn.sparkfun.com/tutorials/re-programming-the-lilytiny--lilytwinkle)_ from SparkFun.

I installed Arduino IDE, setup the LilyTiny board interface and I am ready to start coding, or am I?

Here is my initial setup
<center>
<img src="{{ site.url }}/images/LilyTiny_setup_1.jpg" alt="LilyTiny initial setup" width="200px"/>
</center>

I used the _Hello world_ program suggested in the tutorial, hit the upload and Yikes! 😥

<center>
<img src="{{ site.url }}/images/LilyTiny_error_1.jpg" alt="LilyTiny initial setup" width="200px"/>
</center>

Here is what the error says:

    Arduino: 1.8.10 (Linux), Board: "ATtiny25/45/85, ATtiny25, Internal 1 MHz"
    An error occurred while uploading the sketch
    avrdude: Warning: cannot open USB device: Permission denied
    avrdude: Error: Could not find USBtiny device (0x1781/0xc9f)

__Immediate thought__: Could it be my USB C port that does not recognize the device?

__First try__: I spent some time looking into the error: `avrdude: Error: Could not find USBtiny device (0x1781/0xc9f)`. I found several websites mentioning it. Most of them suggest issue with connectivity: so I tried a different USB cable, tried a different USB port and finally tried a different computer with an _old_ type of USB port (USB A). Not much luck with any of them.

__Second try__: Getting annoyed about the error and lack of a quick fix, I decided to look into the warning: `avrdude: Warning: cannot open USB device: Permission denied`. Well, lessor learned: read the warning and pay attention to them! If the software has no permission to access the device, it can not communicate with it. The fix from [Andeas Rohner's blog post](https://andreasrohner.at/posts/Electronics/How-to-fix-device-permissions-for-the-USBasp-programmer/) worked like a charm. I am now getting the message "Done uploading" 😀
