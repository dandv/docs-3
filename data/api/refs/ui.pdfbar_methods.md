Methods
=======

{{api
- api/link/ui.pdfbar_addview.md - add new view to layout-like component
- api/link/ui.pdfbar_adjust.md - adjusts the component to the size of the parent HTML container
- api/link/ui.pdfbar_attachevent.md - attaches the handler to an inner event of the component (allows behaviour customizations)
- api/link/ui.pdfbar_bind.md - binds components
- api/link/ui.pdfbar_blockevent.md - temporarily blocks triggering of ALL events of the calling object
- api/link/ui.pdfbar_callevent.md - calls an inner event
- api/link/ui.pdfbar_clear.md - clears all the field in a specified form
- api/link/ui.pdfbar_clearvalidation.md - removes "data incorrect" highlighting from invalid text fields
- api/link/ui.pdfbar_define.md - redefines a single configuration property (or a hash of properties)
- api/link/ui.pdfbar_destructor.md - destructs the calling object
- api/link/ui.pdfbar_detachevent.md - detaches a handler from an event (which was attached before by the attachEvent method)
- api/link/ui.pdfbar_disable.md - disables the calling view (makes it dimmed and unclickable)
- api/link/ui.pdfbar_enable.md - enables the calling view that was disabled by the 'disable' method
- api/link/ui.pdfbar_focus.md - sets focus into the necessary component
- api/link/ui.pdfbar_getchildviews.md - returns child views of the calling component
- api/link/ui.pdfbar_getcleanvalues.md - returns hash of original form values
- api/link/ui.pdfbar_getdirtyvalues.md - returns hash of changed values
- api/link/ui.pdfbar_getformview.md - returns master form for the input
- api/link/ui.pdfbar_getnode.md - returns the main HTML container for the calling object
- api/link/ui.pdfbar_getparentview.md - returns the parent view of the component
- api/link/ui.pdfbar_getscrollstate.md - returns the scroll position
- api/link/ui.pdfbar_gettopparentview.md - returns top parent view
- api/link/ui.pdfbar_getvalues.md - derives input values from the form
- api/link/ui.pdfbar_hasevent.md - checks whether the component has the specified event
- api/link/ui.pdfbar_hide.md - hides the view
- api/link/ui.pdfbar_index.md - returns the cell index in the layout collection
- api/link/ui.pdfbar_isdirty.md - checks whether changes within form were made
- api/link/ui.pdfbar_isenabled.md - checks whether the view is enabled
- api/link/ui.pdfbar_isvisible.md - checks whether the view is visible
- api/link/ui.pdfbar_load.md - loads data from an external data source.
- api/link/ui.pdfbar_mapevent.md - routes events from one object to another
- api/link/ui.pdfbar_markinvalid.md - marks a form control invalid
- api/ui.pdfbar_navigate.md - 
- api/link/ui.pdfbar_parse.md - loads data to the component from an inline data source
- api/link/ui.pdfbar_reconstruct.md - rebuilds the layout
- api/link/ui.pdfbar_refresh.md - repaints the component
- api/link/ui.pdfbar_removeview.md - removes view from layout-like component
- api/link/ui.pdfbar_render.md - renders the specified item or the whole component
- api/link/ui.pdfbar_resize.md - adjusts the view to a new size
- api/link/ui.pdfbar_resizechildren.md - resizes all children of the calling component
- api/link/ui.pdfbar_scrollto.md - scrolls the data container to a certain position
- api/link/ui.pdfbar_setdirty.md - marks the form as the one with changed values and vice versa
- api/ui.pdfbar_setmasterpage.md - 
- api/ui.pdfbar_setmasterscale.md - 
- api/ui.pdfbar_setpage.md - 
- api/ui.pdfbar_setpages.md - 
- api/ui.pdfbar_setscale.md - 
- api/link/ui.pdfbar_setvalues.md - sets values into the inputs of a form/toolbar/property sheet control
- api/link/ui.pdfbar_show.md - makes the component visible
- api/link/ui.pdfbar_showbatch.md - makes visible those elements which parameter 'batch' is set to the specified name
- api/link/ui.pdfbar_unbind.md - breaks "bind" link
- api/link/ui.pdfbar_unblockevent.md - cancels blocking events that was enabled by the 'blockEvent' command
- api/ui.pdfbar_updatecontrols.md - 
- api/link/ui.pdfbar_validate.md - checks data in the component during adding new item or editing existing ones
- api/ui.pdfbar_zoom.md - 
}}

@index:
- api/link/ui.pdfbar_addview.md
- api/link/ui.pdfbar_adjust.md
- api/link/ui.pdfbar_attachevent.md
- api/link/ui.pdfbar_bind.md
- api/link/ui.pdfbar_blockevent.md
- api/link/ui.pdfbar_callevent.md
- api/link/ui.pdfbar_clear.md
- api/link/ui.pdfbar_clearvalidation.md
- api/link/ui.pdfbar_define.md
- api/link/ui.pdfbar_destructor.md
- api/link/ui.pdfbar_detachevent.md
- api/link/ui.pdfbar_disable.md
- api/link/ui.pdfbar_enable.md
- api/link/ui.pdfbar_focus.md
- api/link/ui.pdfbar_getchildviews.md
- api/link/ui.pdfbar_getcleanvalues.md
- api/link/ui.pdfbar_getdirtyvalues.md
- api/link/ui.pdfbar_getformview.md
- api/link/ui.pdfbar_getnode.md
- api/link/ui.pdfbar_getparentview.md
- api/link/ui.pdfbar_getscrollstate.md
- api/link/ui.pdfbar_gettopparentview.md
- api/link/ui.pdfbar_getvalues.md
- api/link/ui.pdfbar_hasevent.md
- api/link/ui.pdfbar_hide.md
- api/link/ui.pdfbar_index.md
- api/link/ui.pdfbar_isdirty.md
- api/link/ui.pdfbar_isenabled.md
- api/link/ui.pdfbar_isvisible.md
- api/link/ui.pdfbar_load.md
- api/link/ui.pdfbar_mapevent.md
- api/link/ui.pdfbar_markinvalid.md
- api/ui.pdfbar_navigate.md
- api/link/ui.pdfbar_parse.md
- api/link/ui.pdfbar_reconstruct.md
- api/link/ui.pdfbar_refresh.md
- api/link/ui.pdfbar_removeview.md
- api/link/ui.pdfbar_render.md
- api/link/ui.pdfbar_resize.md
- api/link/ui.pdfbar_resizechildren.md
- api/link/ui.pdfbar_scrollto.md
- api/link/ui.pdfbar_setdirty.md
- api/ui.pdfbar_setmasterpage.md
- api/ui.pdfbar_setmasterscale.md
- api/ui.pdfbar_setpage.md
- api/ui.pdfbar_setpages.md
- api/ui.pdfbar_setscale.md
- api/link/ui.pdfbar_setvalues.md
- api/link/ui.pdfbar_show.md
- api/link/ui.pdfbar_showbatch.md
- api/link/ui.pdfbar_unbind.md
- api/link/ui.pdfbar_unblockevent.md
- api/ui.pdfbar_updatecontrols.md
- api/link/ui.pdfbar_validate.md
- api/ui.pdfbar_zoom.md

