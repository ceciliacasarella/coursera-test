# CSS Lecture 14: Combining Selectors

*Element*, *Class* and *ID* **Selectors**.

## 1 Element with Class selector 

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

## Descendant Selector

> Every p element that is inside (at any level) of **article**

```css
article p {
	color: blue;
} 
```
# p element affected 

```html
<article>
	<div>...</div>
	<p>...</p>
</article> 
```

# p element affected (any level)

```html
<article>
	<div>
		<p>...</p>
	</div>
</article>
```
## Child Selector

> Every p element that is a **direct** child of **article**

```css
article > p {
	color: blue;
} 
```
# p element affected 

```html
<article>
	<div>...</div>
	<p>...</p>
</article> 
```

# Not affected 

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

> Quote
> > Nested quote 