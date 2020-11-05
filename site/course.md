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

