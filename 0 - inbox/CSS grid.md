---
status: newBorn
related-links: 
created: 2025-06-15T14:29
updated: 2025-06-15T15:58
---
---
> use to control two axis at the same time


![[Pasted image 20250615143301.png||550]]

**Grid terminologies**
- green one is grid cell
- blue one is grid track
- pink one is grid area
- parent element ( the border we have ) is grid container ( basically a div most of the times)
- yellow ones are grid lines

**codes**
- this code will create 4 rows of 40px and 2 columns of 60px 
```css
body{
	display: grid;
	grid-template-rows: 40px 40px 40px 40px;
	grid-template-columns: 60px 60px
}
```

##### `repeat()` function of CSS grid
- this code will create 10 rows of 40px and 6 columns of 40px
- by using `repeat()` function of css we don't have to write again and again to create a large grid
```css
body{
	display: grid;
	grid-template-rows: repeat(10, 40px);
	grid-template-columns: repat(6, 40px);
}
```

- spreading items using row and column
	- normally end is exclusive
	- with span ( means jitta lee sakta hai lele ) to any number inclusive
	- also take negative column
![[Pasted image 20250615152351.png||500]]
![[Pasted image 20250615153340.png||500]]
- [[code copy block note#grid code]]
- [CSS Grid Layout](https://www.w3schools.com/css/css_grid.asp)
	- in this method, we first set `grid-template-areas` to set a template
	- then we use `grid-area: <areaname>` on element classes or id to tell which element is associated to which area

