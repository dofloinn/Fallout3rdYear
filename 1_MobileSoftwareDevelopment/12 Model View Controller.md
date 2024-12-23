### <mark style="background: #AD21D9;">Model View Controller S/W Architecture Pattern:</mark>

![](https://i.imgur.com/X4i15pf.png)

### <mark style="background: #AD21D9;">Structuring your code and classes:</mark> 

When you create your various classes in an application, you want to:  
- Promote reusability (e.g. panels for OK/Cancel buttons might be used in several screens)  
- Minimise code maintenance when something changes (e.g. dB structure, new GUI device )  
- Maintain as much flexibility as possible

### <mark style="background: #AD21D9;">Model view controller:</mark>  

<mark style="background: #AD21D9;">MVC</mark> is a common S/W Architecture pattern used for interactive applications (i.e. applications that have a Graphical User Interface)  

<mark style="background: #AD21D9;">Model:</mark> Classes that deal with storing and using data  

<mark style="background: #AD21D9;">View:</mark> Classes or code that deal with the GUI part  

<mark style="background: #AD21D9;">Controller:</mark> (Non graphical) classes that bridge the View and the Model

### <mark style="background: #AD21D9;">MVC:</mark> 

<mark style="background: #AD21D9;">Philosophy:</mark> Keep the parts that may be re-used elsewhere or changed SEPARATE

Similar approach to internet layers:
![](https://i.imgur.com/dz4Z2DZ.png)

We need to keep the layers independent and loose so the changes in the code of one layer do not affect the other modules.

### <mark style="background: #AD21D9;">Model:</mark>  

<mark style="background: #AD21D9;">Model:</mark> classes that deal with storing and using data  

If data structure(s) or rules change... Just change these classes  

Can have multiple different GUIs using the same model?  
- E.g. calculator functions add/subtract, etc  
- Different GUIs (standard web, accessible web, etc)

### <mark style="background: #AD21D9;">View</mark> 

<mark style="background: #AD21D9;">View:</mark> classes that deal with the GUI part  

If the GUI layout changes, don’t (necessarily) need to change the model or control classes  

E.g. change borders of buttons

### <mark style="background: #AD21D9;">Controller:</mark> 

<mark style="background: #AD21D9;">Controller:</mark> (non graphical) classes that bridge the View and the Model  

<mark style="background: #AD21D9;">Kept separate:</mark>  
- Listener classes that trigger behaviour  
- Generally consists of everything that is not the layout or not directly storing/using data

### <mark style="background: #AD21D9;">MVC - Philosophy:</mark>  

<mark style="background: #AD21D9;">Separation of components for:</mark>  
- Reuse – e.g. supposing two different screens in Android have same appearance?  
- Maintainability e.g. supposing I want to change colours of all my screen. Does the kotlin code change?

### <mark style="background: #AD21D9;">Does Android Support MVC S/W architecture pattern?</mark> 

Somewhat.  

Abstracted screen layouts...View  

Easy to maintain if changed without necessarily changing M/C parts  

Static resources are kept separate from dynamic code . . . bit of model  

Dynamic model code.. developer determines E.g. put database code into separate classes from the activity  

Controller code?

### <mark style="background: #AD21D9;">Example:</mark>

![](https://i.imgur.com/aslUbxj.png)

<mark style="background: #AD21D9;">App:</mark> this screen displays a list of tourist destinations

### <mark style="background: #AD21D9;">MVC - List Example:</mark>  

Classes /layouts needed?  

<mark style="background: #AD21D9;">For View bit:</mark>
- Listview Layout to display list etc  
- Row layout  

<mark style="background: #AD21D9;">For Model bit:</mark>  
- What “data” is involved? What can be done to it? Is there a dB involved?  
- Put dB connection/operations into separate class(es) to the activity – then other activities can use this class for dB connection and operations and code is centralised  

<mark style="background: #AD21D9;">For Controller bit:</mark>  
- What’s needed apart from GUI and doing the model part? Activity...

### <mark style="background: #AD21D9;">Other things:</mark> 

<mark style="background: #AD21D9;">Giant all purpose class for everything – wrong!</mark>  
- Hard to maintain  
- Nothing reusable  

<mark style="background: #AD21D9;">Decide which “parts” might be reusable</mark>  
- E.g. database code  
- Parts of screen (OK/Cancel panels) – Android supplies ``<Fragment>``  

<mark style="background: #AD21D9;">Keep MVC as a guiding principle but as with any design:</mark>  
- There is no single “right” answer to how you break your app into classes  
- But design in advance, rather than just letting your code wander along in a single class or two...  

<mark style="background: #AD21D9;">MVC is one S/W architecture and some techniques we’ve seen contradict it</mark>  
- E.g. implementing listeners directly in the activity code  
- Anonymous listeners – embedded against the GUI component – has its own advantages..  
- These approaches have their own merits..  
- Be aware of the trade offs.