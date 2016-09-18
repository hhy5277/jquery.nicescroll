#jQuery.NiceScroll
v. 3.6.8 02-29-2016

 - [Web Site: nicescroll.areaaperta.com](http://nicescroll.areaaperta.com)
 - [Repo: github.com/inuyaksa/jquery.nicescroll](https://github.com/inuyaksa/jquery.nicescroll)
 - [Twitter: @nicescroll](https://twitter.com/nicescroll)

 [![Join the chat at https://gitter.im/inuyaksa/jquery.nicescroll](https://badges.gitter.im/inuyaksa/jquery.nicescroll.svg)](https://gitter.im/inuyaksa/jquery.nicescroll?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

> Nicescroll as a Greasemonkey plugin: http://userscripts.org/scripts/show/119910 (freezed)


> Nicescroll is a jquery plugin, for nice scrollbars with a very similar ios/mobile style.

  - HORIZONAL scrollbar support!
  - It supports DIVs, IFrames, textarea, and document page (body) scrollbars.
  - Compatible with all desktop browser: Firefox 4+, Chrome 5+, Safari 4+ (win/mac), Opera 10+, IE 6+. (all A-grade browsers)
  - Compatible with mobile device: iPad/iPhone/iPod, Android 2.2+, Blackberry phones and Playbook (WebWorks/Table OS), Windows Phone 7.5 Mango.
  - Compatible with all touch devices: iPad, Android tablets, Window Surface.
  - Compabible with multi-input device (mouse with touch or pen): Window Surface, Chrome Desktop on touch notebook.
  - Compatible with 2 directions mice: Apple Magic Mouse, Apple Mouser with 2-dir wheel, PC mouse with 2-dir wheel (if browser support it).

So you have scrollable divs with momentum for iPad 4+ and you have consistent scrollable areas for all desktop and mobile platforms.

Sexy zoom feature, you can "zoom-in" the content of any nicescroll'ed div.
Nice to use and nice to see, all the content of the div in fullscreen mode.
It works on desktop (double click on div) either in mobile/touch devices using pinch gesture.

On modern browsers hardware accelerated scrolling has implemented.
Using animationFrame for a smoothest and cpu-saving scrolling. (when browser supports)

"Use strict" tested script for maximum code quality.
Bower and AMD ready.

Warning for IE6 users (why do you uses IE6 yet? Please updgrade to a more stable and modern browser), some feature can't work for limitation of the browser.
Document (body) scrollbars can't appears, old (native browser) one is used. Some issues with IFrame scrolling.


## FEATURES

- simple installation and activation, it works with NO modification of your code. (some exceptions can happen, so you can write to me)
- very stylish scrollbars, with no occupation on your window (original browser scrollbars need some of page space and reduces window/div usable width)
- you can style main document scrollbar (body) too!! (not all script implements this feature)
- on all browsers you can scroll: dragging the cursor, mouse wheel (speed customizable), keyboard navigation (cursor keys, pagup/down keys, home/end keys)
- scroll is smooth (as modern tablet browsing), speed is customizable
- zoom feature
- hardware accelerated scroll (where available)
- animation frame support for smoth scrolling and cpu-saving
- dragging scroll mode with scrolling momentum (as touch device)
- tested for all major browsers desktop and mobile versions
- support for touch devices
- support for multi-input devices (IE10 with MSPointer)
- compatible with many other browsers, including IE6, Safari on Mac and WP7 Mango!
- very customizable aspect of bar
- native scroll events are working yet
- fully integrated with jQuery
- compatibile with jQuery UI, jQuery Touch, jQuery Mobile


## DEPENDENCIES
>> It's a plugin for the jquery framework, you need to include jquery in your scripts.
>> From 1.5.x version and on. (I'd better to use 1.8.3+ minimum)


* INSTALLATION
Put loading script tag after jquery script tag and loading the zoom image in the same folder of the script:

<script src="jquery.nicescroll.js"></script>

Copy image "zoomico.png" in the same folder of jquery.nicescroll.js.


* HOW TO USE

Initialize nicescroll ALWAYS in (document) ready statement.
```javascript
// 1. Simple mode, it styles document scrollbar:
$(document).ready(function() {  
    $("html").niceScroll();
});

// 2. Instance with object returned:
var nice = false;
$(document).ready(function() {  
    nice = $("html").niceScroll();
});

// 3. Style a DIV and chage cursor color:
$(document).ready(function() {  
    $("#thisdiv").niceScroll({cursorcolor:"#00F"});
});

// 4. DIV with "wrapper", formed by two divs, the first is the vieport, the latter is the content:
$(document).ready(function() {
    $("#viewportdiv").niceScroll("#wrapperdiv",{cursorcolor:"#00F"});
});

// 5. Get nicescroll object:
var nice = $("#mydiv").getNiceScroll();

// 6. Hide scrollbars:
$("#mydiv").getNiceScroll().hide();

// 7. Check for scrollbars resize (when content or position have changed):
$("#mydiv").getNiceScroll().resize();

// 8. Scrolling to a position:
$("#mydiv").getNiceScroll(0).doScrollLeft(x, duration); // Scroll X Axis
$("#mydiv").getNiceScroll(0).doScrollTop(y, duration); // Scroll Y Axis
```

## CONFIGURATION PARAMETERS
When you call "niceScroll" you can pass some parameters to custom visual aspects:

```javascript
$("#thisdiv").niceScroll({
    cursorcolor: "#424242", // change cursor color in hex 十六进制改变光标颜色，默认值是“＃000000” 
    cursoropacitymin: 0, // change opacity when cursor is inactive (scrollabar "hidden" state), range from 1 to 0 //改变不透明度非常光标处于非活动状态（scrollabar“隐藏”状态），范围从1到0, 默认为0（隐藏） 
    cursoropacitymax: 1, // change opacity when cursor is active (scrollabar "visible" state), range from 1 to 0
    //改变不透明度非常光标处于活动状态（scrollabar“可见”状态），范围从1到0，默认值是1（完全不透明）  
    cursorwidth: "5px", // cursor width in pixel (you can also write "5px") 像素光标的宽度，默认值为5
    cursorborder: "1px solid #fff", // css definition for cursor border 游标边框css定义，默认为“1px的固体＃FFF” 
    cursorborderradius: "5px", // border radius in pixel for cursor 以像素为光标边界半径
    zindex: "auto" | <number>, // change z-index for scrollbar div 改变z-index值的滚动条的div，默认值是9999 
    scrollspeed: 60, // scrolling speed 滚动速度，默认值为60 
    mousescrollstep: 40, // scrolling speed with mouse wheel (pixel) 高速滚动鼠标滚轮，默认值是40（像素） 
    touchbehavior: false, // enable cursor-drag scrolling like touch devices in desktop computer
    //使光标拖动滚动像在台式电脑触摸设备（默认：false） 
    hwacceleration: true, // use hardware accelerated scroll when supported 使用硬件加速滚动支持的时候（默认：true） 
    boxzoom: false, // enable zoom for box content 使变焦框中的内容（默认：false）
    dblclickzoom: true, // (only when boxzoom=true) zoom activated when double click on box 
    //（仅当boxzoom = TRUE）变焦激活时，双击对话框（默认：true） 
    gesturezoom: true, // (only when boxzoom=true and with touch devices) zoom activated when pinch out/in on box
    //（仅当boxzoom =真实，使用触摸设备）上缩放框激活时，间距输出/输入（默认：true） 
    grabcursorenabled: true // (only when touchbehavior=true) display "grab" icon
    //显示“抢”图标的div touchbehavior = true时，（默认：true） 
    autohidemode: true, // how hide the scrollbar works, possible values: 
    //如何隐藏滚动条的作品，真=默认/“光标”=只进游标隐藏/ false =不隐藏背景，CSS改变轨道的背景下，默认为“” 
      true | // hide when no scrolling
      "cursor" | // only cursor hidden
      false | // do not hide,
      "leave" | // hide only if pointer leaves content
      "hidden" | // hide always
      "scroll", // show only on scroll          
    background: "", // change css for rail background
    iframeautoresize: true, // autoresize iframe on load event 在加载事件AUTORESIZE的iframe（默认：true） 
    cursorminheight: 32, // set the minimum cursor height (pixel) 设置在像素的最小光标高度（默认值：20） 
    preservenativescrolling: true, // you can scroll native scrollable areas with mouse, bubbling mouse wheel event
    //您可以滚动本机可滚动区域用鼠标，冒泡鼠标滚轮事件（默认：true） 
    railoffset: false, // you can add offset top/left for rail position 
    //您可以添加抵消顶部/左边的轨道位置（默认：false） 
    bouncescroll: false, // (only hw accell) enable scroll bouncing at the end of content as mobile-like 
    //使滚动弹跳在内容结尾作为移动像（仅HW ACCELL）（默认：false） 
    spacebarenabled: true, // enable page down scrolling when space bar has pressed
    //使向下翻页时，空格键已经按下滚动（默认：true） 
    railpadding: { top: 0, right: 0, left: 0, bottom: 0 }, // set padding for rail bar
    //设置滚动轨道的填充（默认值：{顶：0，右：0，左：0，下：0}） 
    disableoutline: true, // for chrome browser, disable outline (orange highlight) when selecting a div with nicescroll
    //对于chrome浏览器，停用大纲（橙色hightlight）选择具有nicescroll一个div（默认： true）时， 
    horizrailenabled: true, // nicescroll can manage horizontal scroll nicescroll可以管理水平滚动（默认：true） 
    railalign: right, // alignment of vertical rail 取向垂直导轨（defaul：“右”） 
    railvalign: bottom, // alignment of horizontal rail 对齐水平导轨（defaul：“底部”） 
    enabletranslate3d: true, // nicescroll can use css translate to scroll content  //nicescroll可以使用CSS转换使内容区域滚动（默认：true） 
    enablemousewheel: true, // nicescroll can manage mouse wheel events nicescroll可以管理的鼠标滚轮事件（默认：true） 
    enablekeyboard: true, // nicescroll can manage keyboard events nicescroll可以管理键盘事件（默认：true） 
    smoothscroll: true, // scroll with ease movement 平滑滚动（默认：true） 
    sensitiverail: true, // click on rail make a scroll 点击轨道时进行滚动（默认：true）
    enablemouselockapi: true, // can use mouse caption lock API (same issue on object dragging)
    //可以用鼠标说明锁的API（对象拖动同样的问题）（默认：true） 
    cursorfixedheight: false, // set fixed height for cursor in pixel 用于光标以像素设置固定的高度（默认：false） 
    hidecursordelay: 400, // set the delay in microseconds to fading out scrollbars //设置在微秒淡出滚动条的延迟时间（默认值：400） 
    directionlockdeadzone: 6, // dead zone in pixels for direction lock activation
    //在对方向锁定激活像素死区（默认值：6）
    nativeparentscrolling: true, // detect bottom of content and let parent to scroll, as native scroll does
    //检测内容底部，并让父级容器来滚动，像原生滚动那样（默认：true）
    enablescrollonselection: true, // enable auto-scrolling of content when selection text
    //启用自动滚动的内容时，选择文本（默认：true）
    cursordragspeed: 0.3, // speed of selection when dragged with cursor 拖动鼠标选择的速度
    rtlmode: "auto", // horizontal div scrolling starts at left side 起点在右侧的水平滚动
    cursordragontouch: false, // drag cursor in touch / touchbehavior mode also 触摸设备的拖动
    oneaxismousemode: "auto", // it permits horizontal scrolling with mousewheel on horizontal only content, if false (vertical-only) mousewheel don't scroll horizontally, if value is auto detects two-axis mouse
    //值为true的时候允许通过鼠标滚轮使内容水平滚动，值为false的时候只允许滚轮垂直滚动内容，值为auto可以同时探测两个坐标维度
    scriptpath: "" // define custom path for boxmode icons ("" => same script path)定义自定义的盒模型图标，为空表示相同路径
    preventmultitouchscrolling: true // prevent scrolling on multitouch events 多点触控时，阻止滚动
    disablemutationobserver: false // force MutationObserver disabled  强制变动观察器不可用
});
```

Related projects
----------------

* [Nicescroll for Angular](https://github.com/tushariscoolster/angular-nicescroll)

* LICENSE

## Copyright 2011-16 InuYaksa

######Licensed under the MIT License, http://www.opensource.org/licenses/mit-license.php
######Images used for zoom icons have derived from OLPC interface, http://laptop.org/8.2.0/manual/Browse_ChangingView.html
