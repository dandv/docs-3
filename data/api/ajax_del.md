del
=============

@short: issues a DELETE Ajax request to the server
	
@params:
- url	string	the url to load
- params	object	the hash of parameters that need sending to the server
- callback	function	the callback function


@returns:
- xhr		object		an xmlHttpRequest object


@example:
webix.ajax().del("data.php", { id : "11" }, function(text, xml, xhr){
	//response
	alert(text);
});

@related:
	helpers/ajax_operations.md
    desktop/serverside.md

@template:	api_method
@descr:



The callback function takes 3 parameters:

- **text** - the full text of the response
- **xml** - the response parsed as xml, if applicable
- **xhr** - an xmlHttpRequest object