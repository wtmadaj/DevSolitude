---
title: How to Make a Logo with a Transparent Background For Free
date: 2022-06-20 00:00:00
description: Learn how I created the site's logo using free tools. You'll also learn how to make the background transparent.
featured_image: /assets/img/brand/Contact.svg
author: Wes
---
<span class="badge badge-success">Beginner</span>

Today we're going to create a logo and make the background transparent - and we're going to do it all with **free** tools. 

Not free *trials* of paid services or programs, these are totally free tools. One of them has a paid option - but we don't need it. We can accomplish this
for free thanks to help from other tools.

---
### Tools We'll Be Using
* [Canva](https://www.canva.com){:target="_blank"}
* [GIMP](https://www.gimp.org){:target="_blank"}

---
### Canva [<img src="https://marcas-logos.net/wp-content/uploads/2020/01/Canva-logo.png" style="width: 100px; display: inline;">](https://www.canva.com){:target="_blank"}

##### What is Canva and how to get it

In their own words, "Canva is an online design and publishing tool"[^1]. It's an application that helps easily create visual content that can be used for business cards, logos, infographics, social posts, and much more.
It comes with tons of free templates you can use, combine, and edit (to some extent).


Canva has 3 tiers - **Free**, **Pro**, and **Enterprise**. I've only used the free version - here's what it offers us:
* Tons of free templates
* Ability to export as PNG, MP4, GIF, and more
* Web, desktop & mobile apps

The last point is really nice - you can edit a design on your computer (either the website version or desktop app) and pick up where you left off on a phone or tablet. You'll need to be signed in for this feature,
but this doesn't cost anything if you're using the free version.


Some limitations of the free version:
* Export size limitations
* Cannot remove the background of designs 
* Cannot export as SVG

So we're restricted a bit, but that's not unexpected from a free version of a tool. We can't blow the image up to a large scale, export it as an SVG, or make the background transparent to name a few - 
all things we'd probably want to do. Luckily, we can get around these limitations with some other tools.

Ok, enough chatter. [Click here to head over to Canva's website](https://www.canva.com), then click the "**Get Canva Free**" button. It will ask you to log in or sign up (no credit card needed). 
You can also download the desktop app (if you're on a laptop or desktop). If you're on a phone or tablet, search for Canva in the app store to download it and get walked through the login/sign up process.

##### Creating a logo in Canva
Let's create a simple light bulb logo. First, take a look at the tool itself and create a new blank logo template:

<img src="/assets/img/blog-images/canva-create-new-logo.png">

Canva automatically opened the last project I was working on (this site's branding stuff). But let's start from scratch. Click the "plus" icon in the top toolbar as shown, 
then create a new logo template type by selecting "Logo":

<img src="/assets/img/blog-images/canva-pick-logo-template.png">

Select the "Elements" tab on the left-hand side of the app, then search for "light bulb" to find some images to choose from.

<img src="/assets/img/blog-images/canva-find-light-bulb.png" style="max-width:400px;">

Now, pick whatever logo you'd like. For this example, I chose the first one in the search results. When you click the image you want, it drops into the workspace area on the right.

<br>
<div class="alert alert-warning" role="alert">
    <span class="alert-inner--icon"><i class="fa fa-exclamation-triangle"></i></span>
    <span><strong>See a crown icon?</strong> You can't use these images with a free Canva account.</span>
</div>
<br>

Let's make the image take up as much space as possible by dragging the resize bars to the top and bottom of the page.

<div class="row">
<div class="col-md-6"><img src="/assets/img/blog-images/canva-image-resize.png" style="max-width:400px;"></div>
<div class="col-md-6"><img src="/assets/img/blog-images/canva-image-resized.png" style="max-width:400px;"></div>
</div>

At this point you could alter the image if you wanted. You can change the colors (for some elements), alter the background to anything but transparent, and even add more images or text to the page.

##### Downloading the logo
Now that we have the image selected and resized, we want to make the background transparent. Unless we have a paid account, we cannot do that in Canva.

To get around this limitation, we have to get the image **out** of Canva. In the upper right of the desktop app (and iOS app) is a share button and/or icon. Click it to see the "**Share this design**" window:

<img src="/assets/img/blog-images/canva-share-options.png">

Select "**Download**" to see the next set of options:

<img src="/assets/img/blog-images/canva-download-options.png" style="max-width:400px;">

Since we're using the free version, we are ***only*** able to download at the 500 x 500px size. We also cannot make the background transparent (we already knew this). In the "**File type**" drop down,
we can download as any file type **except** SVG (figures, right?). Select PNG as the file type, then click the "**Download**" button. You'll be able to choose the save location and give it a filename.

<br>
<div class="alert alert-primary" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-folder-17"></i></span>
    <span><strong>Remember the filename and location!</strong> 
    <br>We'll open this image in a different tool - but first we need to <strong>get</strong> that tool. Enter GIMP.</span>
</div>
<br>

---
### GIMP [<img src="https://www.gimp.org/images/frontpage/wilber-big.png" style="width:100px; display:inline;">](https://gimp.org){:target="_blank"}


##### What is GIMP, why we need it, and how to get it
GIMP stands for GNU Image Manipulation Program, and it's a "cross-platform image editor"[^2]. Think Photoshop, but free (!!). It's a very powerful tool that can do **tons** of cool things. 

<div class="alert alert-danger" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-notification-70"></i></span>
    <span><strong>Heads up</strong></span>
    <br><span>Because it's so powerful, GIMP can be overwhelming at first glance. So once we get into the tool, let's just focus on one thing at a time.</span>
</div>
<br>

Since Canva's free version doesn't allow us to remove the background (aka make it transparent), we need a tool that can achieve this. GIMP can do that and much, much more. 

Why make the background transparent, you ask? It will look better. This is how the image would look against a darker background right now:

<div style="background-color: dimgray; text-align: center;">
    <br>
    <img src="/assets/img/blog-images/light-bulb-logo.png" style="width:100px;">
    <br><br>
</div>

Ideally we'd like to **only** see the darker background and the light bulb image, not the white box that surrounds the image. Without editing the image, we're stuck with that white box.

Imagine you're trying to put this logo on a shirt, and that shirt is any color *other* than white - it wouldn't look quite right. So let's get GIMP and remove it.

[Click here to head to GIMP's homepage](https://www.gimp.org){:target="_blank"} and click the red **Download** button. It should walk you through the installation process.

Once complete, fire it up so we can import the light bulb logo for editing.

##### Importing our logo into GIMP



##### Editing the logo in GIMP to create a transparent background


[^1]: [Canva's About page](https://www.canva.com/about/){:target="_blank"}
[^2]: [GIMP homepage](https://www.gimp.org){:target="_blank"}