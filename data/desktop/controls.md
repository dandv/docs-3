Form Controls
=============

Webix delivers a variety of controls that can be placed on the form. 
Depending on the functionality they provide, these controls can be used for entering text, 
selecting an option, date or color, switching between multiview cells, etc.

You can learn more about common controls functionality from the article desktop/controls_guide.md.
The current article describes each form control in details.

<br>

<img style="display:block; margin-left:auto;margin-right:auto;"  src="desktop/form_controls.png"/>


Button {#button}
-----------------

**Standard Buttons**

<img src="desktop/buttons.png"/>

~~~js
{ view:"button", id:"my_button", value:"Button", type:"...", inputWidth:100 } 
//types are descriped below
~~~

{{sample 13_form/01_controls/10_buttons.html }}

**HTML Buttons**

<img src="desktop/html_buttons.png"/>

~~~js
{ view:"button", id:"my_button", value:"Button", type:"htmlbutton"}
~~~

{{sample 02_toolbar/12_styled_buttons.html}}

####Main Button Types

Type of a button defines the way is looks like: 

- base (**no type**) - default button;
- **'form'** - a button for a form (darker than standard);
- **'danger'** - a red button to attract user attention;
- **'prev'** - a button with left arrow;
- **'next'** - a button with right arrow;
- **'htmlbutton'** - a button than can be defined by HTML markup;
- ['image'](#imagebutton) and its variations - a button with an image on it;
- ['icon'](desktop/icon_types.md) and its variations - a button with an icon in it.


####Main properties

- **value** (string) - defines the text displayed on standard buttons (basic, *form*, *danger*, *prev*, *next*);
- **label** (string) - defines the text or/and HTML markup for the button of *imabeButton* and *iconButton* types and their valiarions as well as for *htmlbutton*;
- **width** (number) - sets the width of the button;
- **inputWidth** (number) - sets the width of the text on the button and adjusts button's width to it;
- **image** (string) - sets a path to the button icon;
- **align** (string)- positions a button with relation to a parent view;
- **popup** (string)- defines the ID of a popup window that will be shown on button click;
- **click** (function) - defines a function that will be executed on clicking the button (another possibility is to attach an event to it using the button's ID);
- **css** (string) - name of CSS class applied to a button.

{{note
Specific button types as [imagebutton](#imagebutton) and an [icon button](desktop/icon_types.md) feature images / icons in their bodies and are described separately. 
}}

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.button.html)

##Checkbox {#checkbox}

<img src="desktop/checkbox.png"/>

{{sample 13_form/01_controls/06_checkbox.html }}

Checkbox enables zero, one and more choices from the defined list. 

{{snippet
Checkbox Initialization
}}
~~~js
{ view:"checkbox", id:"field_a", label:"Second age", value:1}
~~~

####Main properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control;
    - **labelWidth** - width of the label container;      
- **labelRight** (string) - set the text of right-hand label. Only checkbox features this functionality;
- **value** (boolean) - defines whether the checkbox is selected by default or not (0 for false, 1 for true); 
- **align** (string)- positions button with relation to a parent view;
- **checkValue** (string) - value of the checkbox in the checked state (1 by default);
- **uncheckValue** (string) - value of the checkbox in the unchecked state (0 by default);

Webix checkbox control is based on standard HTML checkbox  yet some skins use a FontAwesome icon to render it. To switch to a standard HTML checkbox, use **customCheckbox** property: 

~~~js
{ view:"checkbox", customeCheckbox:false} 
~~~

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.checkbox.html)

##Colorpicker {#colorpicker}

<img src="desktop/colorboard.png"/>

{{snippet
Colorpicker Initialization
}}
~~~js
{ view:"colorpicker", label:"Front color", name:"color", value:"#ffaadd" }
~~~

{{sample 24_colorpicker/04_in_form.html }}

<a href="http://webix.com/widget/colorpicker/" title="webix colorpicker widget">Colorpicker</a> is used with ui-related [colorboard](desktop/colorboard.md) that is initialized on clicking the control. Colorpicker allows selecting a color from the board for its further usage. 

####Main Properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container;   
- **value**(hex code) - the initial value of the picker that is changed by picking any color from the colorboard.

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.colorpicker.html)

##Combo {#combo}

<img src="desktop/combo.png"/>

{{sample 13_form/01_controls/09_combo.html }}

Ui-related combo is a text-like field with a popup window that appears as you click the field. A popup displays options for users to select. At the same
time, you can edit the text field and the items will be filtered according to the input values. 

{{snippet
Combo Initialization
}}
~~~js
//short form
{ view:"combo", id:'field_m', label: 'Combo', value:"One", yCount:"3", 
	options:["One", "Two", "Three"]}

//full form
{ view:"combo", id:'field_t', label: 'Combo', value:"1", yCount:"3", 
	options:[	
    {id:1, value:"One"}, 
    {id:2, value:"Two"}, 
    {id:3, value:"Three"}
]}

//server options
{ view:"combo", options:"server/data.json"}
~~~

####Main properties

- **value** (string, number) 
	- within **options** array it sets text value for selectable items;
 	- within Combo constructor it defines the initially selected item of the control (**option ID** in case of a full form, **option text** in case of a short form);
- **placeholder** (string) - defines placeholder for combo input. The control should be inited without an initial value;       
- **yCount** (number) - the number of lines in a popup;
- **options** (array, object, string) - sets the options to choose from;
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container.

####Advanced Combo Configuration 

Combo box control can be customized in a number of ways, e.g.: 

- options can be defined dynamically;
- options can be loaded from serverside;
- template can be changed;
- filtering rule can be changed..

To learn more, go to [Advanced Combo and Richselect Settings](desktop/advanced_combo.md) article. 

####Pro Extensions for Combo 

In the **Webix Pro** edition the control can be extended to show either a **dataview** or **datatable** in the popup:

- desktop/datasuggest.md#usingdatasuggestforformcontrols
- desktop/gridsuggest.md#usinggridsuggestforformcontrols

####Getting Current Value

In case of a full initialization form, the **getValue()** method for combo will return ID of selected option rather than text. Use **getInput()** to get to input object and, hence, the text value.  

~~~js
$$('field_t').getValue(); // ->returns 1

$$('field_t').getInput().value // -> returns "One"
~~~

{{sample 80_docs/unit_items.html}}

####Alternatives to Combo Box

- [richselect](#richselect) - identical to combo in look, but text field is non-editable. 
- [text](#text) coupled with [suggest list](desktop/suggest.md). Indentical to combo in look, but while combo requires selection from a popup list, suggest offers values that can be either chosen or ignored. 

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.combo.html)
    
##Counter {#counter}

Counter is a spin-box helps select a number by clicking "+" and "-" buttons to reach the necessary value. Negative valuies are possible

<img src="desktop/counter.png"/>

{{sample 13_form/01_controls/05_counter.html }}

{{snippet
Counter Initialization
}}
~~~js
{ view:"counter", label:"Age", step: 10, min:21, max:100}
~~~

####Main properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **step** (number) - sets a step to the next value (1 by default);
- **align** (string)- positions a button with relation to the parent view;
- **value** (number) - the initial value of a control. 0 by default;
- **min** (number) - minimal value for a control. 0 by default;
- **max** (number) - maximum value for a control.

{{note
Note that if you set **min** and **max** parameters, the initial conreol value should be within the range. 
}}

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.counter.html)


##Datepicker {#datepicker}

<img src="desktop/date_picker.png"/>

{{sample 13_form/01_controls/13_datepicker.html }}

Datepicker is used in a combination with ui-related [calendar](desktop/calendar.md) that is initialized on clicking the control. It allows choosing a date and, optionally, time in the calendar for their further usage. 

{{snippet
Datepicker initialization
}}
~~~js
{view:"datepicker", date: new Date(2012, 6, 8), label: 'Select Date', timepicker:true} 
~~~
####Main properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **value** (string, obj) - initial value to display in the control input field;   
- **placeholder** (string) - defines placeholder for datepicker input. The control should be inited without an initial value;   
- **timepicker** (boolean) - enables a clock for time selection (*false* by default);
- **date** (function) - new Date() constructor to define the initial date of a calendar. If used without parameters, shows current date;
- **stringResult** (boolean) - sets the data type of value returned by **getValue()/get Values()** methods. If true, it returns date as string. By default the property is *false* and the method returns date object;
- **format** (string) - sets a date format to display in the datepicker field. By default it is "%Y-%m-%d". 
- **type** (string) - (optional) sets the datepicker type; only one alternative type is implemented: "time" - configures datepicker for time selection only (uses webix.i18n.timeFormat as formatting pattern)

{{note
Dates are formatted according to the helpers/date_formatting_methods.md.
}}

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.datepicker.html)

##Fieldset {#fieldset}

<img src="desktop/form_fieldset.png"/>

A grouping control based on HTML *< fieldset >* tag. Creates a group to put controls into and sets a border around the group. 

Can be used to neatly put controls into **layout**:

~~~js
{view:"fieldset", body:{
	rows:[
    	{view:"text", ..}, 
        {view:"button", ..}]
 }
}
~~~

{{sample 13_form/05_extras/02_multiple_fieldsets.html }}

Or, to create a control group within a **form**:

~~~js
{view:"form", elements:[
	{view:"text", ..},
    {view:"fieldset", body:{
    	rows:[
        	{view:"text", ..}, 
        	{view:"datepicker", ..}]}
    }
]} 
~~~

{{sample 13_form/05_extras/01_fieldset.html }}

####Main Properties

- **body** (object) - fieldset body object that contains **rows** or **cols** array with controls;
- **label** (string) - text label of the control group, integrated into border.

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.fieldset.html)
    
##Icon {#icon}

<img src="desktop/icons.png"/>

{{snippet
Icon Initialization
}}
~~~js
{ view:"icon", icon: 'mail', align:"left"}
~~~

####Main properties

- **align** (string) - the alignment of component inside designated area;
- **icon** (string) - a predefined name of an icon, its name. Icons and their names are listed on the [Font Awesome](http://fortawesome.github.io/Font-Awesome/).

Icons in this lib exist in the form of a separate **view** (as described above), as a **button type** and as **CSS class**. Read more about Icon types in the [dedicated chapter of the documentation](desktop/icon_types.md).

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.icon.html)


##Image button {#imagebutton}

<img src="desktop/imagebutton_set.png"/>

{{snippet
Image Button Initialization
}}
~~~js
{ view:"button", type: "image", image:".../img.gif", label: "Image Button"}
~~~

{{sample 02_toolbar/07_toolbar_image_button.html }}

####Main Properties

- **image** (path) - path to the desired image;
- **label** (string) - text on a button by the image;
- **type** (string) - defines the type of a button. Numbers indicate image sizes:
	- *image* - an image with a left-hand label (if any); 
    - *imageTop* - an image with a bottom label;
 	- *imageButton* - a button with an image and a left-hand label:  
    - *imageButtonTop* - a button with an image and a label below the image;
- **width** (number) - sets the width of the entire button including its image and text label.

[Controls Common Functionality](desktop/controls_guide.md)

[Manipulating Groups of Buttons](desktop/button_groups.md)
    
##Label {#label}

<img src="desktop/label.png"/>

Ui-related label is a non-scrollable placeholder for plain text. Like other components, it features specific **label** property that sets text value. 

{{snippet
Label Initialization
}}
~~~js
{ view:"label", label: "Label", inputWidth:100, align:"center"}
~~~

{{sample 13_form/02_api/02_attributes.html}}

####Main properties

- **label** (string) - defines text of the label control;
- **inputWidth** (number) - defines the width of the control;
- **align** (string) - positions the label with relation to the parent view.

Label control can be used to render any user HTML or icons (as well as built-in in Webix FontAwesome icons):

~~~js
{ view:"label", label:"<span class='myCss'>My Label</span>"},
{ view:"label", label:"<span class='webix_icon fa-user'></span> My Label" }
~~~

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.label.html)

##Multiselect

{{pronote
The control is available only in **Webix Pro** edition.
}}

<img src="desktop/multiselect.png"/>

{{sample 60_pro/02_form/02_multiselect.html}}

UI-related multiselect is a select control baed on Webix [richselect](#richselect) and allows selecting multiple option at a time while displaying them in the dedicated 
non-editable input field. 

The control's popup is supplied with a "select" button out of box. 

{{snippet
Multiselect initialization
}}
~~~js
{ view:"multiselect", id:"multi", label:"Participant", options:[
	{ id:1, value:"Alex Brown" },
	{ id:2, value:"Dan Simons" },
	{ ... }				
], value:"1,3" }
~~~

####Main properties

- **value** (string) - the initial value to display in the input field, its ID. The string can be separated by a comma (",") to define multiple values;  
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
    - **labelPosition** (string) - defines label position related to the input field. The only possible value is "top";
- **placeholder** (string) - the initial text in the text field, disappears as you start typing in it;
- **options** (array, object) - defines the set of items to select from. [Details](desktop/controls_guide.md#defininginitialvalues);
- **optionWidth** (number) - defines the width of a popup list. By default, it is adjusted to the control width. 	

####Changing "Select" button text

Multiselect control can be customized via extended configuration of its popup suggest, which is described in the [Advanced Settings of Popup Selectors](desktop/advanced_combo.md) article. 

Multiselect suggest features a **buttonText** property that allows defining any custom text for the button:

~~~js
{view:"multiselect", label:"Participant",options:{
     buttonText:"Done",
     data:[
     	{ id:1, value:"Alex Brown" },
     	{ id:2, value:"Dan Simons" }
     ]
}}
~~~

Another way is to **modify the locale**. 

"Select" button text is taken from the current locale (if other is not stated by **buttonText**, as shown above). The locale can be altered:

~~~js
webix.i18n.controls.select = "Done";
webix.i18n.setLocale(); //apply the locale
~~~

Then all the multiselect instances in the app will be supplied with the "Done" word.

####Accessing popup elements

Multiselect API allows getting to its constituent parts:

~~~js
//button object
multiselect.getPopup().getButton();

//list object
multiselect.getpopup().getList();
~~~

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.multiselect.html)

##Multitext 

{{pronote
The control is available only in **Webix Pro** edition.
}}

<img src="desktop/multitext.png"/>

{{sample 60_pro/02_form/01_multitext.html}}

UI-related multitext is a dynamic control based on standard Webix [text](#text) input. It offers users the possibility to add and delete additional fields on the go. 

{{snippet
Multitext initialization
}}
~~~js
{ view:"multitext", id:"multi", value:'dummy@email.com, mirror@email.com', label:"Email" }
~~~

####Main properties

- **value** (string) - the initial value to display in the input field. The string parts separated by a comma (",") will be put to additional input fields);  
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
    - **labelPosition** (string) - defines label position related to the input field. The only possible value is "top";
- **placeholder** (string) - the initial text in the text field, disappears as you start typing in it;
- **icon** (string) - the control's icon. 

####Field Collection IDs

Each field of a multitext control features its own ID. It can be either a given (for the basic field) or an auto-generated one. 

All the methods of a multitext object can be applied to any field object - the changes will be reflected for the whole control. 

####Adding and removing fields

Multitext API allows [adding](api/ui.multitext_addsection.md) and [removing](api/ui.multitext_removesection.md) additional fields dynamically: 

~~~js
var newFieldId = $$("multi").addSection();

//remove specific field
$$("multi").remove(newFieldId);
//remove all the additional fields
$$("multi").remove();
~~~

Notes:

- Only additional fields can be removed, basic one always remains. 
- The methods can be called from any multitext object from the group. 

####Setting and getting values

Multitext features an extended API for **setting** and **getting** its **values**. 

- [setValue](api/link/ui.multitext_setvalue.md) and [getValue](api/link/ui.multitext_getvalue.md) methods for working with the value of the whole control;
- [setValueHere](api/ui.multitext_setvaluehere.md) and [getValueHere](api/ui.multitext_getvaluehere.md) methods for for working with the value of the first (basic) field. 

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.multitext.html)

##Radio {#radio}

<img src="desktop/radio.png"/>

{{sample 13_form/01_controls/04_radio.html }}

Ui-related radio is a block of severel items with the possibility to check only one of them at a time. 

{{snippet
Radio Initialization
}}
~~~js
{view:"radio", label:"Branch", value:1, options:[
	{ id:1, value:"Master" }, //the initially selected item
	{ id:2, value:"Branch" }
]}              
//short form for options array
 {view:"radio", options:["Master", "Branch"]}
~~~

####Main properties

- **value** (string, number) 
	- within **options** array it sets titles of radiobuttons;
 	- within Radio constructor it defines the initially selected radiobutton;
- **id** (string, number) - used with the radio block as well as with each of its items;
- **options** (array, object) - defines the set of items to select from. [Details](desktop/controls_guide.md#defininginitialvalues).
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **align** (string)- positions button with relation to a parent view;
- **vertical** (boolean) - defines vertical arrangement of radiobuttons.

Webix radio control is based on standard HTML radio  yet some skins use a FontAwesome icon to render it. To switch to a standard HTML radio, use **customRadio** property: 

~~~js
{view:"radio", customRadio:false} 
~~~

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.radio.html)
    
##Richselect {#richselect}

<img src="desktop/richselect.png"/>

{{sample 13_form/01_controls/11_richselect.html }}

Ui-related richselect is a non-editable [combo-box](#combo). 

{{snippet
Richselect Initialization
}}
//full form
~~~js
{view:"richselect",
	id: "list2", label: 'richselect', 
    value:1, yCount:"3", options:[ 
		{id:1, value:"One"}, // the initially selected item
		{id:2, value:"Two"}, 
		{id:3, value:"Three"}
    ]
}
...   
//short  form for options array
{view:"richselect", options:["One", "Two", "Three"]}

//server options
{ view:"richselect", options:"server/data.json"}
~~~

Visually, the **richselect** control consists of a [text input](#text) and [popup window](desktop/popup.md) that contains a standard [list](desktop/list.md) of options in its body. 

Another possibility to create a component with a similar functionality is [attaching a suggest list to a text field](desktop/suggest.md), but in this case, text field will be editable.

####Main Properties

- **value** (string, number) 
	- within **options** array it sets text value for selectable items;
 	- within richselect constructor it defines the initially selected item of the control(**ID** in case of a long form, **text value** in case of a short form of initialization);
- **placeholder** (string) - defines placeholder for richselect input. The control should be inited without an initial value;       
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **options** (array, object, string) - sets the options to choose from in a long or short form. [Details](desktop/controls_guide.md#defininginitialvalues).

####Advanced Richselect configuration 

Richselect control can be customized in a number of ways, e.g.: 

- options can be defined dynamically;
- options can be loaded from serverside;
- template can be changed..

To learn more, go to [Advanced Settings of Popup Selectors](desktop/advanced_combo.md) article. 

####Pro Extensions for Richselect 

In the **Webix Pro** edition the control can be extended to show either a **dataview** or **datatable** in the popup:

- desktop/datasuggest.md#usingdatasuggestforformcontrols
- desktop/gridsuggest.md#usinggridsuggestforformcontrols

####Getting Current Value

In case of a full initialization form, the **getValue()** method for combo will return ID of selected option rather than text. Use **getInput()** to get to input object and, hence, the text value.  

~~~js
$$('field_t').getValue(); // ->returns 1

$$('field_t').getInput().value // -> returns "One"
~~~

{{sample 80_docs/unit_items.html}}

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.richselect.html) 

##Search {#search}

<img src="desktop/search.png"/>

{{sample 02_toolbar/13_search_field.html }}

####Main Properties: 

- **placeholder** (string) - a prompt text displayed in the search field.
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container.

UI-related search looks like an input [text](#text) field with a 'search icon' to indicate that it can be used for filtering data in a data-presenting component to get to the necessary item. 

Filtering function should be written by a developer. See the attached sample for details.

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api/refs/ui.search.md)
    
##Select {#select}

<img src="desktop/select_control.png" />

{{sample 13_form/01_controls/02_select.html }}

Select is a control that allows selection from several items. Looks like a dropdown list. 

{{snippet
Select Initialization
}}
~~~js
// full form
{view:"select", label:"Branch", value:1, options:[
	{id:1, value:"Master" }, // the initially selected value
	{id:2, value:"Release" }
  ], labelAlign:'right' 
}

//short form 
{ view:"select", options:["Master", "Release"]}

//server options
{ view:"select", options:"server/data.json"}
~~~

####Main properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **options** (array, object, string) - defines a set of items to select from;
- **value** (string, number) 
	- within **options** array it sets text values for select items;
 	- within Select constructor it defines the initially selected item of the control (**option ID** in case of a full form, **option text** in case of a long form);
    
**Select option**, a list record, may contain:

- a short string, like "Apple";
- **multi-line text** with html tags. In this case, parent (e.g. toolbar) height should be increased. 

~~~js
"toolbar", height:100,
..... 

options:[
	{id:1,value:"Some long multiline content<ul><li>item1</li><li>item 2</li></ul>"}, 
	{id:2,value:"Papaya" }
]
~~~

{{sample 02_toolbar/20_richselect.html}} 

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.select.html) 
    
##Segmented Button {#segmented}

<img src="desktop/segmented.png"/>

{{sample 13_form/01_controls/07_segmented.html }}

Segmented is an integral button with as many segments as you like. Can be used for switching between [multiview](desktop/multiview.md) cells.

{{snippet
Segmented Initialization
}}
~~~js
{view:"segmented", multiview:true, value:1, options:[
	{ id:"1", value:"Section A" }, // the initially selected segment
	{ id:"2", value:"Section B" }, 
	{ id:"3", value:"Section C" }]
}

//short form for options array
{ view:"segmented", options:["Section A", "Section B", "Section C"]}
~~~

####Main properties

- **multiview** (boolean) - connects the control to the multiview cells, enables switching between these cells;
- **options** (array, object) - defines the buttons (segments) within the control. [Details](desktop/controls_guide.md#defininginitialvalues);
- **value** (string, number) 
	- within **options** array it sets titles for button segments;
 	- within Segmented constructor it defines the initially selected item for the control;
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **selected** (string) - defines the tab that will be visible initially.

[Adding and Deleting Segments (Options) on the Go](desktop/tabs_options.md)

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.segmented.html) 

##Slider {#slider}

<img src="desktop/slider.png">

{{sample 13_form/05_extras/03_slider.html}}

Slider is designed for setting a numeric value from a predefined range of values. It's done by dragging a marker left and right over the value line. 

Negative values are possible.

{{snippet
Slider Initialization
}}
~~~js
{ view:"slider", label:"Level", value:"20", min:10, max: 120; name:"s1"},
~~~

####Main Properties

- **value** (number) - initial value of the control;
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **name** (string) - name of the control used to get its value in the form;
- **step** (number) - distance to the next selectable value (1 by default);
- **min** (number) - minimal value of a slider control. 0 by default. 
- **max** (number) - maximum value of the slider control. 100 by default.
- **title** (template, function) - text label over the slider marker 

{{sample 13_form/05_extras/04_slider_step.html}}.

{{note
Note that if you set **min** and **max** parameters, the initial control **value** should be within their range.
}}

**Slider Title** is based on the current value of the control.

For simple title that displayes current value and **static text**, set a template via **webix.template** class:

~~~js
{view:"slider", title:webix.template("Selected: #value#")}
~~~

For complex title that **changes its text** depending on the current value, define a function template:

~~~js
{view:"slider", title:function(obj){
	var text = obj.value > 20 ? "Minimum level reached. " : ""; //title for values over 20
	return text + "Value: "+ obj.value;} //title for other values
}
~~~

###Slider Events

Make use of slider events to set changing title for a drag marker:

- **onChange** - a common event for all conrtol that fires each time control value changes. For slider it takes place as soon as you **stop dragging** the marker, which sets a new value. 
- **onSlider Drag** - fires each time you drag the marker over the line while paying attention to the changing value. 

~~~js
{view:"slider", on:{
	onChange:function(){
		this.define("title", "Final value " + this.getValue());
		this.refresh();
	},
	onSliderDrag:function(){
		this.define("title", "Dragging... Currently "+this.getValue());
		this.refresh();
	}
}}
~~~

{{sample 13_form/05_extras/05_slider_title.html}}

The new title is set with the help of **define()** method while current value of derived with **getValue()**.  Read more about [Changing Component properies](desktop/redefinition.md). 

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.slider.html)

##Tabbar {#tabbar}

<img src="desktop/tabbar.png" />

{{sample 02_toolbar/02_tabbar.html }} 
<br>
{{sample 13_form/01_controls/08_tabbar.html }}

U-related tabbar is an integral button that allows for changing between views in a [multiview](desktop/multiview.md) layout. Its tabs can be nested with
images and icons. 

{{snippet
Tabbar Initialization
}}
~~~js
rows:[
	{view:"tabbar", id:'tabbar', value: 'listView', multiview:true, options: [
		{ value: 'List', id: 'listView'},
    	{ value: 'Form', id: 'formView'},
    	{ value: 'Empty', id: 'emptyView'}]
	},
	//and then goes multiview
	{cells:[...]}
]    
~~~

####Main properties

- **multiview** (boolean)- if *true*, it links tabs to multiview cells; 
- **options** (array, object) - defines buttons for switching between views. [Details](desktop/controls_guide.md#defininginitialvalues);
- **value** (string) - 
	- within **options** array it sets titles for tabs;
    - within Tabbar constructor it defines the tab that will be shown initially on page loading.
- **type** (string) - if set to "bottom", the tabbar gets other styling, more suitable for tabs placed under the multiview. It can be done by changing the order of layout rows;
- **close** (boolean) - if *true*, the "close" functionality for each tab is provided. Each tab can be closed by clicking a dedicated icon on it. 

**Defining tabs that can be closed**

<img src="desktop/tabs_closable.png"/>

Tabs featuring a **close** property in tabbar **options** array gain the functionality:

~~~js
//all tabs can be closed
{view:"tabbar", close:true, options:[...]}

//only "Tab1" can be closed
{view:"tabbar", options:[
	{id:1, value:"Tab1", close:true},
    {id:1, value:"Tab2"}
]}
~~~

{{sample 20_multiview/11_close_button.html}}

**Defining Icons for the tabs**

<img src="desktop/tabs_icons.png"/>

Icons are defined through additional HTML provided within the tab **value**: 

~~~js
 { view:"tabbar", options: [
	{ value: "<span class='webix_icon fa-film'></span>List", id: 'listView' }
 ]}   
~~~

{{sample 20_multiview/05_tabbar_with_icons.html}}

More about different types of defining icons in Webix you can learn in the desktop/icon_types.md article.

####Advanced Tabbar Usage

- [Adding and Deleting Tabs (Options) on the Go](desktop/tabs_options.md)
- [Dynamic Tabbar](desktop/responsive_tabbar.md)

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.tabbar.html) 
    
##Text {#text}

<img src="desktop/text.png"/>

{{sample 13_form/01_controls/01_text.html }}

Ui-related text control is a one-line input field with a label.

{{snippet
Text Initialization
}}

~~~js
{view:"text", value:'dummy@email.com', label:"Email", labelAlign:'right'},
{view:"text", type:'password', value:'123pass', label:"Password", labelAlign:'right'}
~~~

####Main properties

- **value** (string, integer) - the initial value for a text field, can be editable or readonly on your choice;
- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
    - **labelPosition** (string) - defines label position related to the input field. The only possible value is "top";
- **type** (string)- type of a text field, can be  either "text" by default, or "password" or "email". Type is vital for [HTML5 input data validation](desktop/data_validation.md#html5).
- **placeholder** (string) - the initial text in the text field, disappears as you start typing in it;
- **suggest** (array, string) - collection of suggest values, or the ID of an attached [suggest list](desktop/suggest.md) with these values. 

At the same time, "text" properties can be set via an **attributes** object containing properties that coincide with HTML input tag properties. The object is used for [HTML5 data validation](desktop/data_validation.md#html5). 

- **attributes** (object)
	- **maxlength** (number)  - the maximum quantity of symbols that can be typed into the text field; 
    - **required** (boolean) - indicats whether this field must be filled before the form can be submitted. False by default;
    - **title** (string) -  a prompt message that appears on pointing cursor over the field. 
    
The same is true for textarea.    

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.text.html) 
    
##Textarea {#textarea}

<img src="desktop/textarea.png" />

{{sample 13_form/01_controls/03_textarea.html }}

Ui-related textarea control is a multi-line input field with a label.

{{snippet
Textarea Initialization
}}
~~~js
{ view:"textarea", label:"Note", labelAlign:"right", height:200, value: "type here" }
~~~

####Main properties

- **label** (string) - text label of a control. It can be customized by:
	- **labelAlign** (string) - label alignment towards its container. Possible values are "left" and "right".  In any way, it's placed left to the control; 
    - **labelWidth** (number) - width of the label container; 
- **width, height** (integer) - defines the dimension of the text field;
- **labelAligh** (string) - sets the position of a text label;
- **value** (string) - sets the initial text in the field (replaced by input text later)
- **placeholder** (string) - the initial text in the textarea field, disappears as you start typing in it;
- **attributes** (object) - hash of properties. See [text](#text) description for details. 

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.textarea.html) 
    
##Toggle {#toggle}

<img src="desktop/toggle.png" />

{{sample 13_form/01_controls/14_toggle.html }}

A two-state button that can be not only clicked but pressed. Hence, it has two states - pressed and unpressed (initial), which makes it resemble [checkbox](#checkbox) that also has two states (checked and unchecked). 

If needed, Toggle can change its values for each each state. 

{{snippet
Toggle initialization 
}}
~~~js
{ view:"toggle", type:"iconButton", name:"s4", 
	offIcon:"pause", 
	onIcon:"play",
	offLabel:"Disabled", onLabel:"Enabled" },
~~~

####Main properties
 
- **name** (string) - read-only property, defining the toggle's name. It should be unique within a page;
- **label** (string) -  text on the button body, one and the same for pressed and unpressed states;
- **onLabel** (string) - text label on the button in a pressed state;
- **offLabel** (string) -  text label on the button in an unpressed state;
- **icon** (string) - icon for pressed and unpressed toggle states;
- **onIcon** (string) - icon for a pressed toggle;
- **offIcon** (string) - icon for an unpressed toggle.

Icons taken from the [Font Awesome](http://fortawesome.github.io/Font-Awesome/), so pick the necessary icon name at their site. 

**Toggle Types**

Toggle type is defined by the **type** property. If it isn't defined, a standard button is displayed. For image toggles there exist the following types: 

- **iconButton** for a standard button with an icon;
- **image** for an image with a left-hand label (if any);
- **imageButton** for a standard button with an image and a left-hand label;
- **imageTop** for a picture and a label below it;
- **imageButtonTop** for a standard button with a picture and a label under the picture;
- **next** for a  button with a right-hand arrow;
- **prev**for a button with a left-handed arrow.

**Image Toggle types**

<table class="list" cellspacing="0" cellpadding="5" border="0">
	<tr>
		<td> <code> type:"iconButton" </code> </td>
		<td style="text-align:center;"><img src="desktop/toggleicon.png"/></td>
	</tr>
	<tr>
		<td> <code> type:"image" </code> </td>
		<td style="text-align:center;"><img src="desktop/toggle_image.png"/></td>
	</tr>
	<tr>
		<td> <code> type:"imageButton" </code> </td>
		<td style="text-align:center;"><img src="desktop/toggleimagebut.png"/></td>
	</tr>
	<tr>
		<td> <code> type:"imageTop" </code> </td>
		<td style="text-align:center;"><img src="desktop/toggletop.png"/></td>
	</tr>
	<tr>
		<td> <code> type:"imageButtonTop" </code> </td>
		<td style="text-align:center;"><img src="desktop/togglebuttontop.png"/></td>
	</tr>
</table>

{{sample 13_form/01_controls/14_toggle_images.html}}

[Controls Common Functionality](desktop/controls_guide.md)

[API Reference](api__refs__ui.toggle.html) 

@index:
  - desktop/button_groups.md
  - desktop/suggest.md
  - desktop/responsive_tabbar.md
  - desktop/advanced_combo.md