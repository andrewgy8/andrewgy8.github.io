---
layout:     post
title:      "Icons For Days"
subtitle:   "Extending the IonicIcons Librarywith the full Material Designs icons"
date:       2016-09-14 12:00:00
author:     "Andrew Graham-Yooll"
header-img: "img/post-bg-01.jpg"
---

<p>Let me start off by saying that the folks over at <a href="http://ionicframework.com/docs/v2/getting-started/installation/">Ionic</a> are doing a great job. They are responsive to user issues, requests, and questions.</p>

<p>However, one thing that I beleive the Ionic 2 Framework needs more of are... Icons.</p><p>  How could you have too many, right?</p>

<p>Here, I document the way I set up an Ionic project to handle the element:</p> {% highlight html %} <i class="material-icons">face</i> {% endhighlight %}
<p>to render something like </p>
<p>THIS</p>

<h2 class="section-heading">Summary</h2>
<ol>
	<li>Start an Ionic project</li>
	<li>Get the Material Icons font files</li>
	<li></li>
</ol>

<h2 class="section-heading">The lines</h2>

<p>I assume you have node.js, npm and Ionic configured for simple Ionic Project generation. If not, I will be including a short description on how to get started (or you can visit <a href="http://ionicframework.com/docs/v2/getting-started/installation/">Ionics Quickstart Page</a>.</p>

{% highlight bash %}$ ionic start material-icons --v2
$ cd material-icons
$ ionic serve
{% endhighlight %}

<p>Depending on the way you set up NPM on your device, you might get an error</p>
{% highlight bash %}Error: EACCES: permission denied...
{% endhighlight %}
<p>and you will have to use</p>

{% highlight bash %}$ sudo ionic serve
{% endhighlight %}

<p>Congrats! Your project should be up, running and viewable in your browser.</p>

<h2 class="section-heading">Getting the icons</h2>

<p>Navigate to the <a href="https://github.com/google/material-design-icons/tree/master/iconfont
">Material-Icons repository</a>, and download the latest woff, woff2, wot, ttf, and svg files.</p>

<p>Once downloaded, we need to include them in our app. To do that, we need to understand how the app works.</p>

<p>In Ionic2, the file sturcture setup for you when the command {% highlight bash %}$ ionic start material-icons --v2{% endhighlight %} is used, is fundamentally straight forward. For our purposes in this tutorial, the basic sturucture goes like this: </p>

{% highlight bash %}material-icons <--root
--/app <-- where your code goes       
--/www <-- where your app is built to        
--gulpfile.js <-- what builds your app  
{% endhighlight %}

<p>Yes, I know that there are other things in your file. Let's KISS (keep it stupid simple), and pretend we cant see those other files at the moment. </p>

{% highlight bash %}within /app, you write all your code
		   ||
		   \/
gulpfile.js "sees" your code in /app
		   ||
		   \/		
code in /app is processed from typescript
		   ||
		   \/
placed into /www for your browser/device to read
{% endhighlight %}

<p>Now, you may be asking yourself, "why don't we just put all code into the /www folder?"</p>

<h2 class="section-heading">Experiment Time!</h2>

<p>Well, I  strongly encourage you to try to put the Materia Icons files we downloaded earlier directly into the /www file. If you do, make sure to copy the files and don't just drag and drop.</p>

<p>Once you start your server and see your app in your browser, look back in your editor and checkout your search your /www file for the Material Icons file you placed in there. You will notice something that really frustrated me the first time I tried, but it taught me a lot about the process of building an app.</p>

<p>Go ahead and see what happens!</p>

<p>If you do end up going on with this experiment, let us know what happend!</p>

<p>Note: I doubt anything destructive will occur, but if you do something and you can't get your app to function anymore, don't sweat! Just revert back to your last commit, or restart the app.</p>


<h2 class="section-heading">Adjust you gulpfile.js</h2>

<p>If you did the experiment, you should have noticed that the Material Icons folders disappeared when the changes were saved. The reason lies in gulpfile.js...</p>

<p>As we said earlier, the gulpfile is responsible for taking our code or scripts, minifying, and then placing them into the /www. From there, the browser is served the files in the /www folder that it needs to produce a view or function.</p>

<p>The issue with our gulpfile.js file, and the reason our files disappeared from the /www folder is that we never told the gulpfile that we wanted those files processed and placed into the /www folder. That is what we are going to do.</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/post-sample-image.jpg" alt="Post Sample Image">
</a>
<span class="caption text-muted">To go places and do things that have never been done before – that’s what living is all about.</span>

<p>Space, the final frontier. These are the voyages of the Starship Enterprise. Its five-year mission: to explore strange new worlds, to seek out new life and new civilizations, to boldly go where no man has gone before.</p>

<p>As I stand out here in the wonders of the unknown at Hadley, I sort of realize there’s a fundamental truth to our nature, Man must explore, and this is exploration at its greatest.</p>

<p>Placeholder text by <a href="http://spaceipsum.com/">Space Ipsum</a>. Photographs by <a href="https://www.flickr.com/photos/nasacommons/">NASA on The Commons</a>.</p>
