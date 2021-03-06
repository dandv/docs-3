Menu
=============

##API Reference

- [Methods, properties and events](api__refs__ui.menu.html)
- [Samples](http://docs.webix.com/samples/03_menu/index.html)

##Overview

UI-related pulldown **Menu** inherits from [list](desktop/list.md) and lets users select the necessary item from the list of grouped items (submenus). Each element of a submenu can start its own submenu. <br>
A dynamic **Submenu** becomes visible only when you put a mouse pointer over the corresponding item of the main menu (on 'onMouseOver' event) and hides as soon as you remove mouse pointer ("onMouseOut"). 

<br>

<img style="display:block; margin-left:auto;margin-right:auto;" src="desktop/menu.png" />

<br>

##Initialization

Menu object is stored in the **data** property. 

~~~js
webix.ui({
		view:"menu",
        id:"my_menu",
		subMenuPos:"right",
        layout:"y",
		data:[ //menu data
			{ value:"Translate...", submenu:[ 
						"English", "Slavic...", "German"]},
            { $template:"Separator" },
			{ value:"Post...", submenu:[ "Facebook", "Google+", "Twitter" ]}
		],
        type:{
              subsign:true,
              height:50
        }           
  });	
~~~

{{sample 03_menu/01_menubar.html }}

####Comments: 

- **subMenuPos** (string) - sets position of pulldown submenus that will appear on mouse over;
- **layout** - sets the arrangement of menu items (**x** for a horizontal menu, **y** for a vertical one)
- **$template:"Separator"** - flag that indicates a separating line between menu elements. Appears once for eaah flag in the place where it is set;
- **type** - object that contains setting for menu items;
	- **subsign** (boolean) - sets an arrow for an item containing a submenu;
- **openAction** (string) - alters the way of submenu opening - **"click"**. If set, you should first click menu item to enable its opening and hiding on "onMouseOver" and "onMouseOut" events.

{{sample 03_menu/11_menu_open_click.html}}

##Working with Menu Items

###Setting Menu Items

A menu/submenu item can be a **text item** including the one that starts its own **submenu** and any **Webix component** specified by ID. 

Menu items are stored in the **data** array, each item being an object. Submenu items are stored in the **submenu** array. Each menu item may have the following attributes: 

- **id** - item id.If omitted, it's given an auto-generated one;
- **value** - defines text value for an item;
- **href** - defines a link for an item;
- **config** - defines configuration of a child submenu popup (if any).

The easiest way to define menu items is to pass them as a simple array:

~~~js
{ view:"menu", data:["Google", "Facebook", "Twitter"] }
~~~

Or an associative one:

~~~js
{ view:"menu", data:[
	{ id:1, value:"Google"}, 
    { id:2, value:"Facebook", id:3, value:"Twitter"
]}
~~~

**Links in Menu Items**

Each menu and submenu item can be supplied with a **link** specified in the data object by **href** and **target** (optional) attributes:

~~~js
view:"menu",
data:[
	{ id:"1", value:"Imitation of Spenser", href: "#verse1", target:"_blank"},
	{ id:"2", value:"The Human Seasons", href: "#verse2"}
]
~~~

If not specified, target will be set as empty string. 

{{sample 03_menu/13_hrefs.html}}

**Configuring Submenus**

Submenu items can be set as an **array of values**:

~~~js
{ id:"2",value:"Translate...", submenu:[ "English", "Slavic", "German" ]},
~~~

Or, as an **array of menu objects**:

~~~js
{ id: "1.2", value:"Slavic...", submenu:[
	{id: "1.2.1", value:"Belarus"},
	{id: "1.2.2", value:"Russian"},
    {id: "1.2.3", value:"Ukranian"}
]}
~~~

Any nested submenu (a popup) can be configured separately with the help of a **config** attribute of its parent: 

~~~js
view:"menu",
data:[
	{ id:"2",value:"Custom...", 
    	config:{
			width:500,
			on:{ 
            	onItemClick:function(id){
					webix.message("Submenu click: "+id);
				}
            }
		},
		submenu:[ "Facebook", "Google+", "Twitter" ]
     }
]
~~~

{{sample 03_menu/12_submenu_config.html}}

**Webix Component as Menu Item**


<img src="desktop/menu_component.png"/>

**Submenu** parameter may point as well to any Webix component that has been initialized previously:

~~~js
webix.ui({
	id:"details1",
	view:"context",	width:300, height:200,
	body:{ content:"html1" }
});

webix.ui({
	view:"menu",
	data:[
		{ value:"HTML 4", submenu:"details1" },
		{ value:"HTML 5", submenu:"details2" }
    ]
});    
~~~

{{sample 03_menu/02_menubar_template.html}}

The same way you can initialize  Webix **submenu** component separately and then point to it within *submenu* property:

~~~js
webix.ui({
	view:"submenu", id:"test", data:[
		{ id:"1.1", value:"English"},
		{ id:"1.3", value:"German"}
	]
});

webix.ui({
	view:"menu",
	data:[
		{ id:"1", value:"Translate...", submenu:"test"},
		{ id:"2", value:"Post..."
	]
});	
~~~

Each submenu item can take its own submenu component. 

###MenuBar

Menu takes after a toolbar in appearance, but you can't embed other controls on a menu toolbar. To do this, init menu and toolbar as neighbouring cols so that they form an integral entity. 

<img src="desktop/menubar.png" />

~~~js
webix.ui({
	cols:[ menu, toolbar ] 
});
~~~

{{sample 03_menu/07_menu_toolbar.html}}

##Hiding and Disabling Menu Items

###Hiding

To hide and show menu item, you should apply **hideItem()** and **showItem()** to the menu component while specifying item ID as function parameter. 

The event that triggers function execution can be **checkbox state change** in the Webix tree populated with the same data as menu, provided that checkbox item ID = related menu item ID. 

~~~js
$$("tree1").attachEvent("onItemCheck",function(id,state){
	if (state) //if checked
		$$("top_menu").hideItem(id);
	else
		$$("top_menu").showItem(id);
});
~~~

As a result, only "unchecked" menu items are shown.

{{sample 03_menu/10_hide_item.html}}

###Disabling

To disable menu item, you should apply special **disableItem()** and **enableItem()** functions to menu passing ID of the necessary item into them. The methods can be triggered by changing state of a 
checkbox which ID equals to the ID of the corresponding menu item. 

~~~js
$$("tree1").attachEvent("onItemCheck",function(id,state){
	if(state) //if checked
		$$("top_menu").disableItem(id);
	else
		$$("top_menu").enableItem(id);
});
~~~

In essence, disabling and enabling is performed via **CSS classes**, that's why menu items get a **template** that helps display normal and disabled item differently: 

~~~js
view:"menu", 
template:function(obj){
	if(obj.disabled)
		return "<span class='disabled'>"+obj.value+"</span>";
	return obj.value;
}
~~~

{{sample 03_menu/09_disable_item.html}}

##Event Handling with Menu and Submenu Items

All menu and submenu items can be accessed by their IDs.

1 . Any item can be accessed directly with **getMenuItem()** method that takes item ID as parameter and returns item object:

~~~js
//getting menu item value by its ID
$$('menu1').getMenuItem(id).value; 
~~~
 
{{sample 03_menu/01_menubar.html}}


2 . At the same time, menu items can be derived through submenu object returned by **getSubMenu()** method for an item with the specified ID. If there's no submenu for an item - an object of the calling component will be returned. 

~~~js
var menu = $$("menu1").getSubMenu(id);
var item = menu.getItem(id).value;
~~~

{{sample 03_menu/02_menubar_template.html}}

Both methods can be used in either of **menu inner events**, for instance, click events:


- **onMenuItemClick** - fires on clicking all menu items regardless of hierarchy level. Ignores disabled items;
- **onItemClick** - standard event that fires on clicking any item of the same hierarchy level. Fires for disabled item as well. 

{{snippet
General "onMenuItemClick" handler
}}
~~~
view:"menu",
data:[...],
on:{
	onMenuItemClick:function(id){
		webix.message("Click: "+this.getMenuItem(id).value);
	}
}
~~~

{{sample 03_menu/01_menubar.html}}

{{snippet
Submenu specific "onItemClick" handler
}}
~~~js
view:"menu",
data:[
	{ id:"1",value:"Custom...",
		config:{
			width:250,
			on: { onItemClick:function(id){
				webix.message("Submenu click: "+id);
			}}
		},
        submenu:{...}
    }
]

~~~


{{sample 03_menu/12_submenu_config.html }}




##Related Articles

- [Event Handling](desktop/event_handling.md)
- [ContextMenu](desktop/contextmenu.md)
- [Menu CSS Image Map](desktop/menu_css.md)
