onAfterContextMenu
=============


@short:
	fires after the context menu was called in the item area

@params:
- id	   string		the id of the clicked item
- e	 event		a native event object
- node		element		the target HTML element

@example:
$$('list').attachEvent('onAfterContextMenu', function(id, e, node){
     webix.message("Right mouse button was pressed");
});

@relatedapi:
	api/mouseevents_onbeforecontextmenu_event.md
@related:
	desktop/contextmenu.md
@template:	api_event
@descr:

