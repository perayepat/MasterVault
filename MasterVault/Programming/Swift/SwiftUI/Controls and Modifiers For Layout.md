Modifiers stack so the last on effects the modifiers above it 
# Space modifiers 
Links :
[`Spacing Views`](https://betterprogramming.pub/how-to-evenly-space-views-in-swiftui-260965280368)
[`Apple Doc`](https://developer.apple.com/documentation/swiftui/spacer)

Using Spacers , stack spacing  and alignment 

**Spacer**
Spacers are mainly used for layout purposes to separate elements 
```                                                               SwiftUI
VStack {  
Image(systemName: "shield.fill")  
Spacer()  
}

```
![[Pasted image 20220430154237.png]]

# Color Modifiers
Color Modifiers are used to change the color of text and SF Symbol icons 
``` SwiftUI
HStack{
	Text("Hi")
	.foregroundColor(.accentColor)
}
.background(Color(.gray))
```
![[Pasted image 20220430155210.png]]
 Other Color modifiers include :
	 .background 
	 can be placed on the text but will hide the text color placing it on the hstack or vstack will act more as a background.

	  ![[Pasted image 20220430155436.png]]
	 


# Text Modifiers
Links: [`Documentation`](https://developer.apple.com/documentation/swiftui/text)

These modifiers are commonly used to change the weight of your font 
E.g

Makes your text bold
``` Swift
Text("Fonty")
	.font(.bold)
```

and the same can be applied when making your text *Light* or *Italic*

If you need more control for your fonts and want a specific look 
``` Swift
Text("by William Shakespeare")
.font(.system(size: 12, weight: .light, design: .serif))
.italic()
```
This code gives you this:
![[Pasted image 20220430160405.png]]

**Frame Modifier**

When tight on space and you need to fit your text into a tight spots for a specific look 
the frame modifier can be used :

``` Swift
	Text("To be, or not to be, that is the question:") 
	.frame(width: 100)
```
![[Pasted image 20220430160655.png]]


**Line Limit**

When you need your text to trail of and save space the line limit can be used to make sure your text doesn't trail off into the next line. 

``` Swift
	Text("Brevity is the soul of wit.") 
	.frame(width: 100) 
	.lineLimit(1)
```
![[Pasted image 20220430160901.png]]

# Images and effects 
These modifies can also apply to stacks with background 

**Corner Radius**
this will corner the edges of your images 

``` Swift
Image("Landscape_4")
.cornerRadius(10)
```
![[Pasted image 20220430161227.png]]


**Shadow**

this will add a drop shadow the your image 
``` Swift
Image("Landscape_4")
.cornerRadius(10)
.shadow(color: Color.black.opacity(0.5), radius: 5, x: 4, y: 5)
```
![[Pasted image 20220430161544.png]]

**Borders**

This adds a border around your image 
``` Swift
Image("Landscape_4")
.cornerRadius(10)
.border(Color(.black), width:4)
.shadow(color: Color.black.opacity(0.5), radius: 5, x: 4, y: 5)
```

![[Pasted image 20220430161741.png]]

if you place the border before the corner radius then it would have had currved corners 

**Clip Shapes**

``` Swift
Image("Landscape_4")
.ClipShape(Circle())
.shadow(color: Color.black.opacity(0.5), radius: 5, x: 4, y: 5)
```

![[Pasted image 20220430161903.png]]


# Size Modifiers 
To have more control over the elements in  your app you could use these , if the spacer doesnt give you the look that you want 

**Layout Priority**
this evenly distributes the elemetns , the higher the number the higher priority it has on the view

This can be used for any other elements like text or images too

``` Swift 
ContentHeaderView()
PageTitleView(tite : "Order Pizza")
MenuListView()
	.layoutPriority(1)
OrderlistView()
	.layoutPriority(1)
```
this give you this :
![[Pasted image 20220430162631.png]]

``` Swift 
ContentHeaderView()
	.layoutPriority(2)
	
PageTitleView(tite : "Order Pizza")

MenuListView()
	.layoutPriority(1)
	
OrderlistView()
	.layoutPriority(1)
```
this gives us this


![[Pasted image 20220430162716.png]]

# Scale modifiers 
Frames are anotehr form of sizing images and stacks 

For the frame modifier to work on image the resizable() needs to go on first 

``` Swift 
Image("Surf Board")
	.resizable()
	.scaledToFit()
```

E.g.

``` Swift 

Image("Surf Board")
	.resizable()
	.frame(height:100)
```
![[Pasted image 20220430163052.png]]

``` Swift 

Image("Surf Board")
	.resizable()
	.frame(width: 200
	
	
	,height:100)
```

This allows you to resize downloaded PNGs or JPGs to fit the size  and scale you want

# Position Modifiers 
The modifier **Offset**
can be used to change the positioning of a text item or a Hstack this can help when using a zstack and you want to position each element to make them readable.

Can also jsut be used to create custom UI and UX 

E.g.

``` Swift 
	Text("Huli Pizza Company")
		.offset(x: -20, y: 30)
```
![[Pasted image 20220430163732.png]]

this moves the text under the the purple line

