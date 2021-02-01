### Presentation

This modification was developed in the OCMOD format, and transforms all of your store's standard URLs into friendly URLs.

One of the great advantages of this modification is that friendly URLs collaborate directly with SEO, and are visually better.

### Installation

 1. Access the link: https://www.opencart.com/index.php?route=marketplace/extension/info&extension_id=22038.
 2. Find the most current version and compatible with your version of OpenCart and download it.
 3. In the store administration, access the menu Extensions → Installer (Extensions → Installer).
 4. On the installer page, click the Upload button and select the file 'todos-urls-amigaveis.ocmod.zip' (which you downloaded from this repository), and wait for the automatic installation to complete.
 5. After installation, access the Extensions → Modifications menu and click on the Refresh button, so that the installed modification is incremented in the store, remembering that it is not the "Update" button of the browser, but yes the "Update" button in blue color next to the orange and red button on the OpenCart screen.

### Configuration

After installation, no configuration is required.
 
#### Correcting error in cart and search

Assuming that your theme uses the same base as the standard OpenCart theme, you need to make a modification to the catalog / view / javascript / common.js file

In the common.js file, locate the lines of code below:

`` js
if (getURLVar ('route') == 'checkout / cart' || getURLVar ('route') == 'checkout / checkout') {
 location = 'index.php? route = checkout / cart';
} else {
 $ ('# cart> ul'). load ('index.php? route = common / cart / info ul li');
}
``

And replace all occurrences of them with the lines of code below:

`` js
var getURlRewrite = $ (location) .attr ('href'). split ('/'). pop ();

if (getURLVar ('route') == 'checkout / cart' || getURLVar ('route') == 'checkout / checkout') {
 location = 'index.php? route = checkout / cart';
} else if (getURlRewrite == 'cart' || getURlRewrite == 'finalize') {
 location = 'cart';
} else {
 $ ('# cart> ul'). load ('index.php? route = common / cart / info ul li');
}
``

Locate the line of code below:

`` js
url = $ ('base'). attr ('href') + 'index.php? route = product / search';
``

And replace all occurrences of it with the line of code below:

`` js
url = $ ('base'). attr ('href') + 'search';
``

Save changes to the file and clear your browser's cache to remove the cached version of the common.js file.

### Uninstallation

To uninstall the modification, in the store administration, go to Extensions → Modifications menu and select the modification with the name 'All friendly URLs', then click the Delete button and the Refresh button ).

### Update

Access the store administration and perform the Uninstall procedure, then perform the Installation procedure.

### Doubts

OCMOD (OpenCart Modification) is native to OpenCart, that is, it is not necessary to install any add-on in OpenCart to use modifications or extensions in the OCMOD format, for more information about OCMOD, follow the link for more information:

https://github.com/opencart/opencart/wiki/Modification-System
