# Context menu without jQuery
Disclaimer: My english is very bad but I hope you will understand me.
## Creating new context menu object
var context_menu = new ContextMenu();
## Simple using
### Items types
Every simple item in context menu should have:

```
item = {
	"name": /*the name of context menu item*/,
	"action": /*this method is called when click on this item*/
};
```

Every submenu item should have:

```
item = {
	"name": /*the name of submenu*/,
	"items": /*an array of items (simple and submenus)*/
};
```
### If you have permanent list of items.
You can create array of items before using context menu. Then you should add it with method **setItems(items)**. For calling context menu:

```
<script> 
	var context_menu = new ContextMenu();
	context_menu.setItems(items);
</script>
<div oncontextmenu="javascript: context_menu.showMenu(event, this);"></div>
```
### If you have to create items by calling context menu.
```
<script>
function createItems() {
	/*your code*/
	return items;
}
</script>
<div oncontextmenu="javascript: context_menu.showMenu(event, this, createItems());"></div>
```  
## Methods
**addItem(item)** - this method adds simple item into context-menu.

**addSubMenu(item)** - this method adds item into context menu which contains submenu.

**removeItemByName(name)** - removes an item from parent menu.

**setItems(items)** - adds items into context menu. Items is an array which can contain simple items and submenus.

**initMenu(parent)** - adds DOMObject of context menu into node parent.

**showMenu(event, parent, [items])** - this method draws context menu on your page.