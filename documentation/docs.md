from examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom PyPI.Package.src.webui.webui import get_new_window_idfrom examples.serve_folder.main import my_window

### Download And Install
```sh
pip install webui2
```


### Minimal Example
```python
from webui import webui

my_window = webui.Window()
my_window.show('<html><script src="webui.js"></script> Hello World! </html>')
webui.wait()
```


### new_window
```python
from webui import webui

# this way of initialization uses "new_window" internally
my_window = webui.Window()

# More code...

webui.wait()
```


### new_window_id
```python
from webui import webui

# this way of initialization uses "new_window_id" internally
my_window = webui.Window(1)

# More code...

webui.wait()
```


### get_new_window_id
```python
from webui import webui

window_id = webui.get_new_window_id()
print(f"Available window ID: {window_id}")
```


### bind
```python
from webui import webui

def my_function(event: webui.Event):
    print("Event received:", event)
    
my_window = webui.Window()
# The bind function returns the bind id. 
# Handling this return is optional.
# my_window.bind("myFunction", my_function)
bind_id = my_window.bind("myFunction", my_function)
print(f"Function bound with ID: {bind_id}")
```


### event
```python
from webui import webui

def events(e: webui.Event):
    print('Hi!, You clicked on ' + e.element + ' element')

my_window = webui.Window()
# Empty ID means all events on all elements
my_window.bind("", events)
```


### get_best_browser
```python   
from webui import webui

my_window = webui.Window()

browser_id = my_window.get_best_browser()
print(f"Recommended browser ID: {browser_id}")
```


### show
```python  
from webui import webui

my_window = webui.Window()

# The "show" function returns true if the window shows 
# with zero problem, False if something went wrong.
# success = my_window.show("<html>...</html>")
# success = my_window.show("index.html")
# success = my_window.show("http://example.com")

# Handling the return is optional.
my_window.show("index.html")
```

### show_browser
```python  
from webui import webui

my_window = webui.Window()

# success = my_window.show_browser("<html>...</html>", webui.Browser.Chrome)
# success = my_window.show_browser("index.html", webui.Browser.Firefox)

# Handling the return is optional.
my_window.show_browser("index.html", webui.Browser.AnyBrowser)
```


### show_wv
```python  
from webui import webui

my_window = webui.Window()

# success = my_window.show_wv("<html>...</html>")
# success = my_window.show_wv("index.html")
# success = my_window.show_wv("http://example.com")

my_window.show_wv("index.html")
```


### set_kiosk
```python  
from webui import webui

my_window = webui.Window()

my_window.set_kiosk(True)    # Enable Kiosk mode
# my_window.set_kiosk(False) # Disable Kiosk mode
```


### wait
```python  
from webui import webui

# Other webui function calls / code...

# At the end of the main driver
webui.wait()  # Wait until all windows are closed before continuing
```


### close
```python  
from webui import webui

my_window = webui.Window()

my_window.close()  # Close the current window.
```


### destroy
```python  
from webui import webui

my_window = webui.Window()

my_window.destroy()  # Close and free resources for the current window.
```


### exit
```python  
from webui import webui

# Other code...

webui.exit()  # Close all WebUI windows and stop waiting
```


### set_root_folder
```python  
from webui import webui

my_window = webui.Window()

# Handling the return boolean is optional.
success = my_window.set_root_folder("/home/Foo/Bar/")
if success:
    print("Root folder set successfully.")
```


### set_default_root_folder
```python  
from webui import webui

# Handling the return boolean is optional.
success = webui.set_default_root_folder("/home/Foo/Bar/")
if success:
    print("Default root folder set successfully.")
```


### set_file_handler
```python  
# In development...
```


### is_shown
```python  
from webui import webui

my_window = webui.Window()

if my_window.is_shown():
    print("The window is still open.")
else:
    print("The window has been closed.")
```


### set_timeout
```python  
from webui import webui

# Set a timeout of 30 seconds for window connections
webui.set_timeout(30)
```


### set_icon
[//]: # (TODO: document)
```python  
from webui import webui

my_window = webui.Window()

my_window.set_icon("<svg>...</svg>", "image/svg+xml")
```


### encode
[//]: # (TODO: document)
```python  
from webui import webui

```


### decode
[//]: # (TODO: document)
```python  
from webui import webui

```


### free
[//]: # (TODO: document)
```python  
from webui import webui

```


### malloc
[//]: # (TODO: document)
```python  
from webui import webui

```


### send_raw
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_hide
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_size
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_position
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_profile
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_proxy
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_url
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_public
[//]: # (TODO: document)
```python  
from webui import webui

```


### navigate
[//]: # (TODO: document)
```python  
from webui import webui

```


### clean
[//]: # (TODO: document)
```python  
from webui import webui

```


### delete_all_profiles
[//]: # (TODO: document)
```python  
from webui import webui

```


### delete_profile
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_parent_process_id
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_child_process_id
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_port
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_config
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_event_blocking
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_tls_certificate
[//]: # (TODO: document)
```python  
from webui import webui

```


### run
[//]: # (TODO: document)
```python  
from webui import webui

```


### script
[//]: # (TODO: document)
```python  
from webui import webui

```


### set_runtime
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_count
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_int_at
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_int
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_float_at
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_float
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_string_at
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_string
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_bool_at
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_bool
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_size_at
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_size
[//]: # (TODO: document)
```python  
from webui import webui

```


### return_int
[//]: # (TODO: document)
```python  
from webui import webui

```


### return_float
[//]: # (TODO: document)
```python  
from webui import webui

```


### return_string
[//]: # (TODO: document)
```python  
from webui import webui

```


### return_bool
[//]: # (TODO: document)
```python  
from webui import webui

```


### open_url
[//]: # (TODO: document)
```python  
from webui import webui

```


### start_server
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_mime_type
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_port
[//]: # (TODO: document)
```python  
from webui import webui

```


### get_free_port
[//]: # (TODO: document)
```python  
from webui import webui

```

