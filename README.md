Live List Search
===========

Live search class that works on li and tr elements, recognizes up, down, enter, click commands.

![Screenshot](http://www.consideropen.com/inprogress/livelistsearch/livelistsearch_screenshot.jpg)

How to use
----------

In its simplest implementation, Live List Search will accept an input and ul ID.  The li elements will now be live searchable.

	searchTags = new LLSearch({
		'inputID'  : 'list_search',                    
		'listID'   : 'tag_wrap'                     
	});
	
By default, the list will also accept up and down arrows, highlighting the current selection.  Also, if you click on an element, it will become selected.

You can also use the included events:
*click*
fires when the the list item is clicked, passes event and current term

*enter*
fires when the user hits enter (while cursor is focused on input), passes event and current term

	searchTags = new LLSearch({
		'inputID'  : 'list_search',                    
		'listID'   : 'tag_wrap',                      
		'searchTermLi' : 'search_term',
		'onEnter' : function(e, term){
			alert(term);
		},
		'onClick' : function(e, term){
			alert(term);
		}
	});