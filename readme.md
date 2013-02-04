
UBBRImages
==========

Example HTML Page
-----------------

```html
<html>
<head>
	<title>Adaptive Images Test</title>
</head>
<body>

<noscript data-img-src="image.jpg" data-img-alt="Alt Text" data-max-vw="640,1024" data-appendix="small,medium" class="img">
	<img src="image.jpg" alt="Alt Text">
</noscript>

<script type="text/javascript">(function(e,t){var n=function(e,t,n){if(e.attachEvent){e["e"+t+n]=n;e[t+n]=function(){e["e"+t+n](window.event)};e.attachEvent("on"+t,e[t+n])}else e.addEventListener(t,n,!1)},r=function(){var n=e,r="inner";if(!("innerWidth"in e)){r="client";n=t.documentElement||t.body}return{width:n[r+"Width"],height:n[r+"Height"]}},i=function(e,t){return e.replace(/\.\w+$/,function(e){return"-"+t+e})},s=function(){var n=!1,s=t.querySelectorAll("noscript.img");if(e.devicePixelRatio>1)n=!0;else{var o="(-o-min-device-pixel-ratio:3/2),(min-resolution:1.5dppx)";e.matchMedia&&e.matchMedia(o).matches&&(n=!0)}for(var u=s.length-1;u>=0;u--){var a=function(e,t){return e.getAttribute(t)},f=s[u],l=a(f,"data-img-src"),c=a(f,"data-appendix"),h=a(f,"data-max-vw"),p=undefined,v=r().width,m=!1,g=a(f,"data-img-id");p=t.getElementById(g);if(!g){p=new Image;m=!0;p.id="img"+u;f.setAttribute("data-img-id",p.id)}if(c&&h){var y=c.split(","),b=h.split(",");for(var E=0;E<Math.min(b.length,y.length);E++){var S=y[E],x=parseInt(b[E]);if(x>=v){l=i(l,S);break}}}n&&(l=i(l,"2x"));p.src!=l&&(p.src=l);if(m){for(var E=f.attributes.length-1;E>=0;E--){var T=f.attributes[E],N=T.name;N.slice(0,8)=="data-img"&&N!="data-img-src"&&p.setAttribute(N.slice(9),T.value)}f.parentNode.insertBefore(p,f)}}};s();n(e,"resize",s)})(window,document);</script>
</body>

</html>
```

Usage
-----
Use a _noscript_ element, like the one in the example, in every position where you usally would use an _img_-tag and don't forget to set the class to _"img"_.


When the browser reaches the end of the html document and executes the script, it will make the browser request:

* __image-small.jpg__ when the viewport width <= 640 and pixel density < 1.5
* __image-medium.jpg__ when the viewport width <= 1024 and pixel density < 1.5
* __image.jpg__ when the viewport width > 1024 and pixel density < 1.5
* __image-small-2x.jpg__ when the viewport width <= 640 and pixel density > 1.5
* __image-medium-2x.jpg__ when the viewport width <= 1024 and pixel density > 1.5
* __image-2x.jpg__ when the viewport > 1024 and pixel density < 1.5






The MIT License
---------------

Copyright (c) 2013 Karsten Bruns (karsten{at}bruns{dot}me)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.