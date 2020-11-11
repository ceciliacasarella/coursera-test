# CSS Lecture 14: Combining Selectors

*Element*, *Class* and *ID* **Selectors**.

# 1 Element with Class selector 

> Every p Paragraph that has **class = "big"**

```css
p.big {
	font-size: 20px;
} 
```

```html
<p class="big">...</p>
<div>...</div>
<p>...</p>
```

# Descendant Selector

> Every p element that is inside (at any level) of **article**

```css
article p {
	color: blue;
} 
```
## p element affected 

```html
<article>
	<div>...</div>
	<p>...</p>
</article> 
```

## p element affected (any level)

```html
<article>
	<div>
		<p>...</p>
	</div>
</article>
```
# Child Selector

> Every p element that is a **direct** child of **article**

```css
article > p {
	color: blue;
} 
```
## p element affected 

```html
<article>
	<div>...</div>
	<p>...</p>
</article> 
```

## Not affected 

```html
<article>
	<div>
		<p>...</p>
	</div>
</article>
```

## Not limited To Element Selector

> Every p that is inside (at any level) an element with **class ="colored"**

```css
.colored p {
	color: blue;
} 
```
> Every element with class = "colored" that is a **direct** child of **article** element

```css
article > .colored {
	color: blue;
} 
```
### Summary 

Combining selectors:
1. Element with *class* selector (selector.class)
2. *Child* (direct) selector (selector > selector)
3. *Descendent* selector (selector selector) 


# CSS Lecture 15: Pseudo-Class Selector

Pseudo-class selectors address targeting only the structures that can be targeted by simple combinations of regular selectors, or targeting the ability to style based on user interaction with the page. 

> User hovers or moves the mouse over the element.

### The definition
```css
selector.pseudo-class {
	...
} 
```

Many pseudo-class selectors already exist:
1. **:link**
2. **:visited**
3. **:hover**
4. **:active**
5. **:nht-child(...)**

```css
		a:link, a:visited{
			text-decoration: none;
			background-color: green;
			border: 1px solid blue;
			display: block;
			width: 200px;
			text-align: center;
			margin-bottom: 1px;
		}
```
```css
		a:hover, a:active{
			background-color: red;
			color: purple;
		}

		header li:nth-child(3){
			font-size: 50px;
		}

		section div:nth-child(odd){
			background-color: grey;
		}

		section div:nth-child(4):hover {
			background-color: green;
			cursor: pointer;
		}
```

# CSS Lecture 17: Conflict Resolution

> Cascading is a fundamental feature of CSS.
> As the name itself suggests, cascading style sheets, in other words the cascade algorithm, is at the core of understanding and using CSS. The cascade combine the importance, origin, specificity and source order of the applicable style declarations to determine exactly which declaration should be applied to any given element.
> How to tell which CSS rule wins.

Cascading: how to combine different property values originating from different sources.

Concepts of : *ORIGIN*, *MERGE*, *INHERITANCE*, *SPECIFICITY*.

>Conflict: Origin Precedence : **LAST DECLARATION WINS**.


Lecture 18: Part2 Styling Text 

##Relative font sizing.
> Two units of measurements that are relative that we're going to talk about and that is *percent* and *ems*.

```css
body {
	font-size: 120%
}
```
And what that means is that we want to take whatever the default size is, and by default I mean whatever the browser provides by default, and increase it by 120%.


Lecture 21: Positioning Elements by Floating

> **Important**: when you float elements the browser takes them out of the regualar document flow.

- Margin of floated elements never collapse

BEFORE:

```css
p {
  width: 50px;
  height: 50px;
  border: 1px solid black;
}

#p1 {
  background-color: #A52A2A;
}
#p2 {
  background-color: #DEB887;
}
#p3 {
  background-color: #5F9EA0;
}
#p4 {
  background-color: #FF7F50;
}
```
```css
#p1 {
  background-color: #A52A2A;
  float: right;
}

```
What happens?
The box jumpes all the way to the right, top edge of the containing element. 
The rest of the boxes moved up as if the maroon box isn't there anymore.
Even though each one of these paragraph boxes has a margin around them, that margin collapses when it is touching the margin of another element. 
However, when it comes to floated elements, the margins never collapse.

## Two Columns Design 

```css
p {
  width: 50%;
  border: 1px solid black;
  float: left;
}
```
> - The width of the paragraph p should be 50% of the containing element which is the div.
> - The div is *block level element* so it tries to fill in the entire width of its containing element which is the body or the entire browser.
> - So basically we are saying that the paragraph p should take 50% of the entire view port.
> - Like this it doesn't work: the reason this is happening is because we're still using the default box sizing, which is content box. 
> - Then we're saying that we want the box to take 50% of the screen and then we're adding that one pixel border, that really breaks the whole thing.
##Important: Resetting Block sizing

```css
* {
  box-sizing: border-box;
}
```
And once we do that, the border will be included in the 50% of the width, so now we save the file, we go ahead and refresh, and now we see even with the border we can have both of them floating side by side.

And the reason they're flexible is because we didn't specify them with a particular pixel size, we specified them as a percentage of its container element.

~~~~
* {
  box-sizing: border-box;
}
~~~~



