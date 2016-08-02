Methods
=======

{{api
- api/link/ui.filelist_add.md - adds an item to the store
- api/link/ui.filelist_addcss.md - applied CSS class to a component item
- api/link/ui.filelist_adjust.md - adjusts the component to the size of the parent HTML container
- api/link/ui.filelist_attachevent.md - attaches the handler to an inner event of the component (allows behaviour customizations)
- api/link/ui.filelist_bind.md - binds components
- api/link/ui.filelist_blockevent.md - temporarily blocks triggering of ALL events of the calling object
- api/link/ui.filelist_callevent.md - calls an inner event
- api/link/ui.filelist_clearall.md - removes all items from the component
- api/link/ui.filelist_clearcss.md - removes css class from all items
- api/link/ui.filelist_clearvalidation.md - removes all validation marks from the component
- api/link/ui.filelist_copy.md - copies an item to the same or another object
- api/link/ui.filelist_count.md - returns the number of currently visible items
- api/link/ui.filelist_customize.md - redefines the "type" property
- api/link/ui.filelist_define.md - redefines a single configuration property (or a hash of properties)
- api/link/ui.filelist_destructor.md - destructs the calling object
- api/link/ui.filelist_detachevent.md - detaches a handler from an event (which was attached before by the attachEvent method)
- api/link/ui.filelist_disable.md - disables the calling view (makes it dimmed and unclickable)
- api/link/ui.filelist_edit.md - enables the edit mode for the specified item
- api/link/ui.filelist_editcancel.md - cancels the edit mode and closes all opened editors. The component is still editable
- api/link/ui.filelist_editnext.md - closes the current editor and opens one in the next cell of the row
- api/link/ui.filelist_editstop.md - stops the edit mode and closes all opened editors. The component is still editable
- api/link/ui.filelist_enable.md - enables the calling view that was disabled by the 'disable' method
- api/link/ui.filelist_exists.md - checks whether an item with the specified id exists
- api/link/ui.filelist_filter.md - filters the component
- api/link/ui.filelist_find.md - returns rows that match the criterion
- api/link/ui.filelist_focuseditor.md - moves focus to the active editor
- api/link/ui.filelist_getchildviews.md - returns child views of the calling component
- api/link/ui.filelist_geteditstate.md - returns info about active editor object
- api/link/ui.filelist_geteditor.md - returns editor object
- api/link/ui.filelist_geteditorvalue.md - returns the value of the active (currently open) editor
- api/link/ui.filelist_getfirstid.md - returns the ID of the first item
- api/link/ui.filelist_getformview.md - returns master form for the input
- api/link/ui.filelist_getidbyindex.md - returns the id of the item with the specified index
- api/link/ui.filelist_getindexbyid.md - returns the index of the item with the specified id
- api/link/ui.filelist_getitem.md - gets the object of the data item with the specified id
- api/link/ui.filelist_getitemnode.md - returns HTML element of the item
- api/link/ui.filelist_getlastid.md - returns the id of the last item
- api/link/ui.filelist_getnextid.md - returns the ID of an item which is positioned the specified step after the specified item
- api/link/ui.filelist_getnode.md - returns the main HTML container for the calling object
- api/link/ui.filelist_getpage.md - returns the currently visible page in case of paged view
- api/link/ui.filelist_getpager.md - returns the pager object associated with the component
- api/link/ui.filelist_getparentview.md - returns the parent view of the component
- api/link/ui.filelist_getprevid.md - returns the ID of an item which is positioned the specified step before the specified item
- api/link/ui.filelist_getscrollstate.md - returns the scroll position
- api/link/ui.filelist_getselectedid.md - returns the id(s) of the selected item(s)
- api/link/ui.filelist_getselecteditem.md - returns selected object
- api/link/ui.filelist_gettopparentview.md - returns top parent view
- api/link/ui.filelist_getvisiblecount.md - returns the number of items that can be seen with the current view height
- api/link/ui.filelist_hascss.md - checks if item has specific css class
- api/link/ui.filelist_hasevent.md - checks whether the component has the specified event
- api/link/ui.filelist_hide.md - hides the view
- api/link/ui.filelist_isenabled.md - checks whether the view is enabled
- api/link/ui.filelist_isselected.md - checks whether the specified item is selected or not
- api/link/ui.filelist_isvisible.md - checks whether the view is visible
- api/link/ui.filelist_load.md - loads data from an external data source.
- api/link/ui.filelist_loadnext.md - sends a request to load the specified number of records to the end of the clientside dataset or to the specified position
- api/link/ui.filelist_locate.md - gets the id of an item from the specified HTML event
- api/link/ui.filelist_mapevent.md - routes events from one object to another
- api/link/ui.filelist_move.md - moves the specified item to the new position
- api/link/ui.filelist_movebottom.md - moves the specified item to the last position
- api/link/ui.filelist_movedown.md - increases the item index and moves the item to the new position
- api/link/ui.filelist_moveselection.md - moves selection in the specified direction
- api/link/ui.filelist_movetop.md - moves the specified item to the first position
- api/link/ui.filelist_moveup.md - decreases the item index and moves the item to the new position
- api/link/ui.filelist_parse.md - loads data to the component from an inline data source
- api/link/ui.filelist_refresh.md - repaints the whole view or a certain item
- api/link/ui.filelist_remove.md - removes the specified item/items from datastore
- api/link/ui.filelist_removecss.md - removes CSS class from a component item
- api/link/ui.filelist_render.md - renders the specified item or the whole component
- api/link/ui.filelist_resize.md - adjusts the view to a new size
- api/link/ui.filelist_scrollto.md - scrolls the data container to a certain position
- api/link/ui.filelist_select.md - selects the specified item(s)
- api/link/ui.filelist_selectall.md - selects all items or the specified range
- api/link/ui.filelist_serialize.md - serializes data to a JSON object
- api/link/ui.filelist_setpage.md - makes the specified page visible (assuming that the pager was defined )
- api/link/ui.filelist_show.md - makes the component visible
- api/link/ui.filelist_showitem.md - scrolls the component to make the specified item visible
- api/link/ui.filelist_sort.md - sorts datastore
- api/link/ui.filelist_sync.md - allows syncing two copies of data (all or just a part of it) from one DataCollection to another
- api/link/ui.filelist_unbind.md - breaks "bind" link
- api/link/ui.filelist_unblockevent.md - cancels blocking events that was enabled by the 'blockEvent' command
- api/link/ui.filelist_unselect.md - removes selection from the specified item
- api/link/ui.filelist_unselectall.md - removes selection from all items
- api/link/ui.filelist_updateitem.md - sets properties of the data item
- api/link/ui.filelist_validate.md - validates one record or all dataset against validation rules
- api/link/ui.filelist_validateeditor.md - validates data in currently active editor
}}

@index:
- api/link/ui.filelist_add.md
- api/link/ui.filelist_addcss.md
- api/link/ui.filelist_adjust.md
- api/link/ui.filelist_attachevent.md
- api/link/ui.filelist_bind.md
- api/link/ui.filelist_blockevent.md
- api/link/ui.filelist_callevent.md
- api/link/ui.filelist_clearall.md
- api/link/ui.filelist_clearcss.md
- api/link/ui.filelist_clearvalidation.md
- api/link/ui.filelist_copy.md
- api/link/ui.filelist_count.md
- api/link/ui.filelist_customize.md
- api/link/ui.filelist_define.md
- api/link/ui.filelist_destructor.md
- api/link/ui.filelist_detachevent.md
- api/link/ui.filelist_disable.md
- api/link/ui.filelist_edit.md
- api/link/ui.filelist_editcancel.md
- api/link/ui.filelist_editnext.md
- api/link/ui.filelist_editstop.md
- api/link/ui.filelist_enable.md
- api/link/ui.filelist_exists.md
- api/link/ui.filelist_filter.md
- api/link/ui.filelist_find.md
- api/link/ui.filelist_focuseditor.md
- api/link/ui.filelist_getchildviews.md
- api/link/ui.filelist_geteditstate.md
- api/link/ui.filelist_geteditor.md
- api/link/ui.filelist_geteditorvalue.md
- api/link/ui.filelist_getfirstid.md
- api/link/ui.filelist_getformview.md
- api/link/ui.filelist_getidbyindex.md
- api/link/ui.filelist_getindexbyid.md
- api/link/ui.filelist_getitem.md
- api/link/ui.filelist_getitemnode.md
- api/link/ui.filelist_getlastid.md
- api/link/ui.filelist_getnextid.md
- api/link/ui.filelist_getnode.md
- api/link/ui.filelist_getpage.md
- api/link/ui.filelist_getpager.md
- api/link/ui.filelist_getparentview.md
- api/link/ui.filelist_getprevid.md
- api/link/ui.filelist_getscrollstate.md
- api/link/ui.filelist_getselectedid.md
- api/link/ui.filelist_getselecteditem.md
- api/link/ui.filelist_gettopparentview.md
- api/link/ui.filelist_getvisiblecount.md
- api/link/ui.filelist_hascss.md
- api/link/ui.filelist_hasevent.md
- api/link/ui.filelist_hide.md
- api/link/ui.filelist_isenabled.md
- api/link/ui.filelist_isselected.md
- api/link/ui.filelist_isvisible.md
- api/link/ui.filelist_load.md
- api/link/ui.filelist_loadnext.md
- api/link/ui.filelist_locate.md
- api/link/ui.filelist_mapevent.md
- api/link/ui.filelist_move.md
- api/link/ui.filelist_movebottom.md
- api/link/ui.filelist_movedown.md
- api/link/ui.filelist_moveselection.md
- api/link/ui.filelist_movetop.md
- api/link/ui.filelist_moveup.md
- api/link/ui.filelist_parse.md
- api/link/ui.filelist_refresh.md
- api/link/ui.filelist_remove.md
- api/link/ui.filelist_removecss.md
- api/link/ui.filelist_render.md
- api/link/ui.filelist_resize.md
- api/link/ui.filelist_scrollto.md
- api/link/ui.filelist_select.md
- api/link/ui.filelist_selectall.md
- api/link/ui.filelist_serialize.md
- api/link/ui.filelist_setpage.md
- api/link/ui.filelist_show.md
- api/link/ui.filelist_showitem.md
- api/link/ui.filelist_sort.md
- api/link/ui.filelist_sync.md
- api/link/ui.filelist_unbind.md
- api/link/ui.filelist_unblockevent.md
- api/link/ui.filelist_unselect.md
- api/link/ui.filelist_unselectall.md
- api/link/ui.filelist_updateitem.md
- api/link/ui.filelist_validate.md
- api/link/ui.filelist_validateeditor.md

