---
title: How to Create HTML/CSS Cards and Flashcards
date: 2022-07-17 00:00:00
description: Learn how to create "cards" with HTML and CSS. Then learn how to make them flip over to reveal more content - like a flashcard or flip card.
featured_image: /assets/img/pages/flashcard-header.jpg
author: Wes
---
<span class="badge badge-primary">HTML</span>
<span class="badge badge-success">CSS</span>

Most websites use "cards" to organize and display content. See the "**You might also like...**" section at the bottom of this page? Those are cards. Here's another example:

<div class="card" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Title</h4>
    <h6 class="card-subtitle mb-2 text-muted">Subtitle</h6>
    <p class="card-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
  </div>
</div>

*Cards* aren't stand-alone HTML elements - that's just the description of what the final result will look like. A card. We could call it whatever we want - content box, postcard, index card, whatever - but "card"
happens to be the industry's standard name.

We're going to learn how to make cards and turn them into **flashcards**. So they'll have content on the "front" and flip over to reveal more content on the "back" as if they were real flashcards.

### Why Make Cards?
Cards achieve many things, like:
* Separating content
* Drawing attention to content
* Providing depth to a page

and you can use them for whatever you want:
* Profile information
* Pricing levels
* Restating or calling out important information

When done correctly, they're effective and appealing. Let's get to work and try to achieve that.

---
### Setting Up the HTML for Cards
We have to start with the basic HTML structure before we can create the cards. Here's a bare-bones HTML file:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>Title</title>
	</head>
	<body>

	</body>
</html>
```

<br>
<div class="alert alert-primary" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-hat-3"></i></span>
    <span><strong>Need a crash-course in HTML basics?</strong> 
    <br>Mozilla has an amazing collection of developer resources. Check out their HTML page to get started.</span><br><br>
    <a href="https://developer.mozilla.org/en-US/docs/Web/HTML" class="btn btn-secondary" target="_blank">Mozilla HTML Guides</a>
</div>
<br>

Now let's add a `<div></div>` between the `<body></body>` tags in the HTML we just created. Let's nest another div inside 
the div we just created. Next, assign the outer and inner div **distinct** class names (this lets us target each of them with CSS later). And for filler text we can put 
some lorem ipsum in a `<p></p>` inside the inner div. Here's what we've got so far:


```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>Flashcards</title>
	</head>
	<body>

		<div class="card-wrapper">
			<div class="card-body">
				<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do 
                  eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
			</div>
		</div>

	</body>
</html>
```

<br>
<div class="alert alert-info" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-button-pause"></i></span>
    <span><strong>What's lorem ipsum???</strong> 
    <br>It's filler text. We use it as a placeholder for previewing layouts, designs, mockups, or whatever. It keeps focus on the design instead of the text.</span><br><br>
    <a href="https://lipsum.com" class="btn btn-secondary" target="_blank">Learn more & generate here</a>
</div>
<br>

If you open this file in a browser, you'll see that it doesn't look *anything* like a card. Here's how it would look right now:

<div class="card-wrapper">
			<div class="card-body">
				<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
			</div>
</div>


Not what we're looking for, but that's how it always starts before adding CSS. Let's add some styling to fancy it up a bit.

---
### Adding Some Initial CSS
Turning this into a card is actually pretty easy. We'll set the width of the `card-wrapper` to a fixed amount and add a box-shadow for some depth. Then we'll add some padding
to the `card-body` so the text within the card isn't edge-to-edge. Here's the CSS of these changes:

```css
.card-wrapper {
    box-shadow: 0 15px 35px rgba(0,0,0,0.2),0 5px 15px rgba(0,0,0,0.19);
    width: 25rem;
    }
.card-body {
    padding: 5px 15px;
    }
```

And here's the result:

<div class="card-wrapper" style="box-shadow: 0 15px 35px rgba(0,0,0,0.2),0 5px 15px rgba(0,0,0,0.19); width: 25rem;">
    <div class="card-body" style="padding: 5px 15px;">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
    </div>
</div>
<br>

Good news - it's looking like a card. Now let's make it have a "front" and "back."

<br>
<div class="alert alert-success" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-check-bold"></i></span>
    <span><strong>What if I don't want cards that flip over?</strong> 
    <br>If you don't want cards that flip over like flashcards, then you're done! </span><br><br>
</div>
<br>

---
### Making the Card Front and Back
To create a "front" and "back" for the card, we'll need to add some more `div`s. We'll have a `div` that wraps the entire "front" content, and then a 
`div` that wraps the entire "back" content. Once that structure is in place, CSS is all we need to make the "flip" effect.

#### Card front and back HTML
First let's add the HTML for the 2 sides of the card (and assign class names) and add some filler `<p>` text in the front and back:

```html
<div class="card-wrapper">
  <div class="card-body">
    <div class="card-front">
      <p>Lorem ipsum dolor?</p>
    </div>
    <div class="card-back">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
    </div>
  </div>
</div>
```

I moved the existing filler lorem ipsum text to sit inside `<div class="card-back>` and added a short filler inside `<div class="card-front">` so it
will (eventually) look like a question-answer flashcard. But it's not there yet, the result of this is still a one-sided card:

<div class="card-wrapper" style="box-shadow: 0 15px 35px rgba(0,0,0,0.2),0 5px 15px rgba(0,0,0,0.19); width: 25rem;">
  <div class="card-body" style="padding: 5px 15px;">
    <div class="card-front">
      <p>Lorem ipsum dolor?</p>
    </div>
    <div class="card-back">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
    </div>
  </div>
</div>
<br>

CSS is going to solve this.

#### Card front and back CSS
To get the flip effect, we're going to need a bit more CSS. It's actually around *5 times* more CSS, but don't worry - we'll walk through it. And heads-up: the CSS
we applied earlier? Some of that will move and some of it will go away altogether.

<br>
<div class="alert alert-info" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-bell-55"></i></span>
    <span><strong>Here's how these next sections will flow</strong>
    <ul>
        <li>The CSS will be shown in a code block</li>
        <li>We'll talk through what that CSS is <i>actually</i> doing</li>
    </ul>
    The goal is for you to understand it. That way you can change it according to <i>your</i> needs.</span><br>
</div>

##### The card wrapper
```css
.card-wrapper {
    width: 25rem;
    height: 200px;
}
```

This section is styling the outer div of the card: `<div class="card-wrapper">`.

###### Width
`width` sets how wide the card is, or the horizontal size. 

You can use a number of values for setting width (and height). In this case, `width: 25rem;` means that the width of the card
will be 25 times the size of the root font-size. So if the CSS declares that the default font-size for the HTML document is 16px, then `25rem` would be:

25 times 16px = 400px 

<br>
<div class="alert alert-primary" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-hat-3"></i></span>
    <span><strong>CSS Units: rem and em</strong> 
    <br>Among units you can use in CSS for sizing, "<strong>em</strong>" and "<strong>rem</strong>" are some of the more confusing ones. Check out these (external) articles that 
    offer some great explanations.</span><br><br>
    <a href="https://designshack.net/articles/typography/whats-the-deal-with-em-and-rem/" class="btn btn-secondary" target="_blank">"What's the deal with em and rem?" (Design Shack)</a>
    <br><br><a href="https://www.digitalocean.com/community/tutorials/css-rem-vs-em-units" class="btn btn-secondary" target="_blank">"rem vs em units in CSS" (Digital Ocean)</a>
</div>
<br>

###### Height
`height` sets how tall the card is, or the vertical size. We're using a fixed height in this case.

If you need the cards to grow according to their content, it might be better to use something like `min-height`. You can also set a `max-height` if 
you need it - it's common to use both of these together.

##### The card body
```css
.card-body {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 15px 35px rgba(0,0,0,0.2),0 5px 15px rgba(0,0,0,0.19);
}

.card-wrapper:hover .card-body {
    transform: rotateX(180deg);
}
```

These sections are styling the body of the card.

###### position
`position` sets the position of the element. `position: relative;` means it will be positioned in the normal flow of the document and offset relative to itself when used with `top`,
 `right`, `bottom`, and/or `left`. So if you also set `left: 100px;`, then the element will have 100px added to the left position (or be "pushed" 100px to the *right*).

<div class="alert alert-warning" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-lock-circle-open"></i></span>
    <span><strong>Note that we are NOT setting "top", "right", "bottom", or "left" here.</strong>
    <br>There's an additional use case. If an element has its <code style="color: black;">position</code> set to <code style="color: black;">absolute</code>, then it will be positioned
    <i>relative to the nearest positioned ancestor</i>. We'll come back to this in a minute.</span><br>
</div>

###### width and height
`width` and `height` are used to set the size like we did in the `card-wrapper`. This time we set these to `100%`. Since the parent element of `card-body` is `card-wrapper`, we 
can use this value to make sure the child element takes up the entire space available to its parent. In other words, the `card-body` will be the same size as the `card-wrapper`.

###### text-align
`text-align` sets the alignment of the text. This text you're reading would be `text-align: left;`. The text in the cards is centered - so we use `center`.

###### transition
`transition` gives us a way to *change some CSS values over a period of time*. We're going to `transform` this element over `.6s` (just over half a second). We'll set the `transform` animation
later (spoiler alert: it's going to flip over like a flashcard).

###### transform-style
`transform-style` allows us to specify if we want the child elements to preserve 3D position or not. We want to set it as `preserve-3d` so that the text flips over and is not upside down or backwards.

###### box-shadow
`box-shadow` gives a shadow effect around the element. We used this earlier in `card-wrapper` and are just moving it to the `card-body`. If we left it on the other element, the flip effect would
look like the text on the card is flipping over instead of the entire card flipping over.

###### transform (upon hovering over the card wrapper)
`.card-wrapper:hover .card-body { ... }` in plain English says: "When a user hovers their mouse over the card-wrapper, the card-body will then have the following style." We are going to set a 
style that is **applied only when you hover over a specific element**.

So when you hover over the card, we want it to flip over. We do that by setting the `transform` property we talked about within `transform-style` earlier to `transform: rotateX(180deg);`. 

We want to *transform* the card body by *rotating it 180 degrees along the X-axis (horizontal axis)*. So we're flipping it over similar to flipping a coin in the air.

If we set it to `rotateY(180deg)` it would rotate along the Y-axis, or vertical axis. This would be like spinning that same coin on a table instead of flipping it in the air.
I just happened to pick rotateX in this case.

If we set the degrees to 360, the card would flip over and land back on the same side - not what we're looking for in this case.

##### Card front and back
```css
.card-front, .card-back {
    background-color: #ffffff;
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    -webkit-backface-visibility: hidden;
}
.card-front p, .card-back p {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
    font-size: large;
    margin: 0;
}
.card-back {
    transform: rotateX(180deg);
}
```

These sections are styling the front and back of the card along with the `<p>` elements within them.

###### background-color, width, height
We've seen these before, so let's cover these first. We're setting the `background-color` to white in hex format. We're also making sure
the front and back of the card are the same size as their parent element by setting `width` and `height` to `100%`.

###### position: card front and back
<div class="alert alert-warning" role="alert">
    <span class="alert-inner--icon"><i class="ni ni-key-25"></i></span>
    <span><strong>Remember how I said we'd come back to something in a minute?</strong>
    <br>That minute is now.</span><br>
</div>


We've seen `position` before: earlier we set the `card-body` to `position: relative;`. We also talked about how `relative` is used with 
`top`, `right`, `bottom`, and `left`. But we're not using any of those - instead we set it earlier so that it would allow us to set its 
value here to `absolute`.

Since we explicitly set the parent element to `position: relative;` we can now be certain that any child elements with `position: absolute;` will be 
*confined within the bounds of the parent element*. 

So the `card-front` and `card-back` are now on top of each other - like a deck of cards. 

###### backface-visibility
the back face is the mirror image of the front face. We don't want that to be visible, so we set it to `hidden`. 
 
`-webkit-backface-visibility` is the same as `backface-visibility`, but is added to make sure certain browser display properly (like Chrome and Safari).

###### position: <p> elements in card front and back
`.card-front p, .card-back p` means we're setting the style for `<p>` elements that are children of either `card-front` or `card-back`. We want them to 
be positioned relative so that we can center them vertically - which we'll talk about next.

###### top & transform
`top: 50%` and `transform: translateY(-50%)` is like a magic trick that centers the targeted element vertically when used along with `position: relative;`.

It pushes the element down by 50% of its containing element from the top (with the `top` value), then pushes it up by 50% of the space from the bottom. We'll need both so
that the center of the body of text is also centered on the back or front.

###### font-size
This one's easy - set the text size.

###### margin
This zeros the margin of the element (since we set it to `0`). It actually works to make sure the `<p>` elements are centered vertically in this case.

###### transform the card back
```css
.card-back {
    transform: rotateX(180deg);
}
```

A good way to explain this is that this *puts the content meant for the back of the card actually on the back of the card*. It does this by rotating the `card-back` 180 degrees. 

Remember how we set `backface-visibility: hidden;`? Since the back faces are hidden, flipping the `card-back` 180 degrees **now** means the back face of the `card-back` is
facing forward - but we can't see it.

Once we hover, the front rotates 180 degrees and its back face becomes hidden. At the same time, the back rotates and its front face becomes visible. A flashcard!


---
### Results and Full Code
Here's the final card in all its glory:

{% include flashcard.html %}

<br>

And here's the code in a single HTML document:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>Flashcards</title>
		<style>
			.card-wrapper {
              width: 25rem;
              height: 200px;
            }
			.card-body {
              position: relative;
              width: 100%;
              height: 100%;
              text-align: center;
              transition: transform 0.6s;
              transform-style: preserve-3d;
              box-shadow: 0 15px 35px rgba(0,0,0,0.2),0 5px 15px rgba(0,0,0,0.19);
			}
			.card-front, .card-back {
              background-color: #ffffff;
      		  position: absolute;
              width: 100%;
              height: 100%;
              backface-visibility: hidden;
              -webkit-backface-visibility: hidden;
			}
			.card-front p, .card-back p {
              position: relative;
              top: 50%;
              transform: translateY(-50%);
              font-size: large;
              margin: 0;
			}
			.card-back {
              transform: rotateX(180deg);
			}
			.card-wrapper:hover .card-body {
              transform: rotateX(180deg);
			}
		</style>
	</head>
	<body>

		<div class="card-wrapper">
			<div class="card-body">
				<div class="card-front">
					<p>lorem ipsum dolor?</p>
				</div>
				<div class="card-back">
					<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
				</div>
			</div>
		</div>
     
	</body>
</html>
```

