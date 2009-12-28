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


Events
----------

You can also use the included events:

**click**
fires when the the list item is clicked, passes event and current term

**enter**
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

Using a table
----------

If you want your list to be a table, you have to set a few parameters.  First, you have to set *listType* to 'tr' and searchTermTr to 'classname' where 'classname is the class associated with the table cell that contains searchable content.  This lets you have a table row where only some content is searchable.

	searchTags = new LLSearch({
		'inputID' : 'list_search',                  
		'listID' : 'tag_wrap',
		'listType' : 'tr',
		'searchTermTr' : 'search_term'
	});

Limiting search in li
----------

You can also limit what you are searching within an li by defining *searchTermLi*.  This is the class of the li child element that contains the search terms.


	searchTags = new LLSearch({
		'inputID' : 'list_search',                  
		'listID' : 'tag_wrap',
		'searchTermLi' : 'search_term'
	});

Other options
----------

**currentSelection** defaults to 'LLS_current_selection', class assigned to current element

**inResultsClass** defaults to 'LLS_inresults', class assigned to elements in list or row to search

**preventClick** default to true, prevents links in the list from being clicked
		
**reFocus** defaults to true, when you click on an entry in the list, this will put the cursor back in the input so there is not an interuption in ability to use up, down and enter key commands.
		