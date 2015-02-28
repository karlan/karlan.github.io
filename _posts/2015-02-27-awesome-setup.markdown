---
layout: post
title:  "AWESOME setup"
date:   2015-02-27 23:00:06
categories: linux
---
[AWESOME][awesome_dm] is my current desktop manager. Personally I hate to use
mouse to click some stupid buttons on the screen. It's inefficient and looks
silly. Though I still have a trackball in hand (I still need to draw some
pictures and play with some interactive programs), I communicate with my
computers via keyboard in 90% of my time. (BTW: For webpage browsing, I use
[vimperator][vimperator] add-on for Firefox and [VimiumPlus][VimiumPlus] for Chrome)

Just some notes about configurations:

## terminal: Xterm

the configuration can be seen in .Xresource(s) in your HOME directory, you may
use
```
      xrdb .Xresources(s)
```
to update your Xterm configuration (you can insert it into your .bashrc or .cshrc file). Below is a sample file based on my .Xresource file, it works great for both English and Chinese fonts.

{% highlight python%}
!look and feel
xterm.termName: xterm-256color
xterm.geometry: 80x36
xterm*scrollBar: false
xterm*rightScrollBar: true
xterm*loginshell: true
xterm*cursorBlink: true
xterm*background:   #000033
xterm*foreground:   #FAFAD2
xterm.borderLess: true
xterm.cursorBlink: true
xterm*colorUL: yellow
xterm*colorBD: white
xterm**cursorColor:  #ff0000

!font and locale
xterm*locale: true
xterm.utf8:     true
xterm*utf8Title: true
xterm*fontMenu*fontdefault*Label: Default
!xterm*faceName:Monospace:antialias=True:pixelsize=14
xterm*faceName:luxi mono:antialias=True:pixelsize=14
xterm*boldFont:Sans:style=Bold:pixelsize=13
xterm*faceNameDoublesize:WenQuanYi Zen Hei Mono:antialias=True:pixelsize=13
xterm*xftAntialias: true
xterm.cjkWidth:true
XTerm*preeditType: Root
{% highlight python%}

In some cases, you will find "_" can not be displayed properly, you need change
`Monspace` to `luxi mono` (as shown above)

## Internet: nmcli

I cannot revoke the NetworkManager Applet in my AWESOME. I have two quick solutions: (1) I can use my android phone to make a USB tether; (2) I can use nmcli, which is the command line verison of NetworkManager

* To check whether NetworkManager is running, type
```
   nmcli -t -f RUNNING nm
```
* To check whether Internet is connected, type
```
    nmcli -t -f STATE nm
```
* To show avaliable network, type

```
    nmcli connection list
```
* To connect a network named "mynet"
```
   nmcli -p con up id "mynet"
```

That's it.


[awesome_dm]:http://awesome.naquadah.org/
[vimperator]:https://addons.mozilla.org/en-us/firefox/addon/vimperator/
[VimiumPlus]:https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb?hl=en
