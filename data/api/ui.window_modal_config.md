modal
=============

@short: switches window modality

@type: bool 
@example:

webix.ui({
	view:"window",
	modal:true,
    ...//config
});

@template:	api_config
@related:
	desktop/window.md
@descr:

By default, Webix window is not modal and its appearance on the page doesn't prevent from working with the main application. 

If modality is set to **true,** users ought to perform actions required by this window before going to the main app. 


