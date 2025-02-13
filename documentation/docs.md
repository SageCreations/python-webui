from examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom examples.serve_folder.main import my_windowfrom PyPI.Package.src.webui.webui import get_new_window_idfrom examples.serve_folder.main import my_window

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
```python  
from webui import webui

my_window = webui.Window()

my_window.set_icon("<svg>...</svg>", "image/svg+xml")
```


### encode
```python  
from webui import webui

encoded_string = webui.ui_encode("Foo Bar")
print(f"Base64 Encoded: {encoded_string}")
```


### decode
```python  
from webui import webui

decoded_string = webui.ui_decode("SGVsbG8=")
print(f"Decoded String: {decoded_string}")  # Output: Hello
```


### free
```python  
from webui import webui

my_buffer = webui.malloc(1024)

webui.free(my_buffer)  # Free the allocated buffer
```


### malloc
```python  
from webui import webui

buffer = webui.malloc(1024)
if buffer:
    print(f"Memory allocated at address: {buffer}")
    webui.free(buffer)  # Free the allocated memory
```


### send_raw
```python  
from webui import webui

my_window = webui.Window()
my_buffer = webui.malloc(1024)

my_window.send_raw("myJavaScriptFunc", my_buffer, 64)
# Sends 64 bytes of raw data to the JavaScript function `myJavaScriptFunc`.
```


### set_hide
```python  
from webui import webui

my_window = webui.Window()

my_window.set_hide(True)  # Hide the window
my_window.set_hide(False) # Show the window
```


### set_size
```python  
from webui import webui

my_window = webui.Window()

my_window.set_size(800, 600)  # Set window size to 800x600 pixels
```


### set_position
```python  
from webui import webui

my_window = webui.Window()

my_window.set_position(100, 100)  # Move window to (100, 100) on the screen
```


### set_profile
```python  
from webui import webui

my_window = webui.Window()

my_window.set_profile("Bar", "/Home/Foo/Bar")  # Use a custom profile
my_window.set_profile("", "")  # Use the default profile
```


### set_proxy
```python  
from webui import webui

my_window = webui.Window()

my_window.set_proxy("http://127.0.0.1:8888")  # Set the proxy server
```


### get_url
```python  
from webui import webui

my_window = webui.Window()

url = my_window.get_url()
print(f"Current URL: {url}")
```


### set_public
```python  
from webui import webui

my_window = webui.Window()

my_window.set_public(True)  # Enable public network access
my_window.set_public(False) # Restrict access to local connections
```


### navigate
```python  
from webui import webui

my_window = webui.Window()

my_window.navigate("http://domain.com")  # Navigate to the specified URL
```


### clean
```python  
from webui import webui

webui.wait()
webui.clean() # Free all WebUI-related resources
```


### delete_all_profiles
```python  
from webui import webui

webui.wait()  
webui.delete_all_profiles()  # Delete all browser profiles
webui.clean()  
```


### delete_profile
```python  
from webui import webui

my_window = webui.Window()

my_window.delete_profile()  # Delete the browser profile for this window
```


### get_parent_process_id
```python  
from webui import webui

my_window = webui.Window()

parent_pid = my_window.get_parent_process_id()
print(f"Parent Process ID: {parent_pid}")
```


### get_child_process_id
```python  
from webui import webui

my_window = webui.Window()

child_pid = my_window.get_child_process_id()
print(f"Child Process ID: {child_pid}")
```


### set_port
```python  
from webui import webui

my_window = webui.Window()

success = my_window.set_port(8080)
if success:
    print("WebUI is now using port 8080.")
else:
    print("Port 8080 is unavailable.")
```


### set_config
```python  
from webui import webui

webui.set_config(webui.Config.show_wait_connection, False)  # Disable waiting for connection
```


### set_event_blocking
```python  
from webui import webui

my_window = webui.Window()

my_window.set_event_blocking(True)  # Enable blocking event processing
my_window.set_event_blocking(False) # Enable non-blocking event processing
```


### set_tls_certificate
```python  
from webui import webui

success = webui.set_tls_certificate(
    "-----BEGIN CERTIFICATE-----\n...",
    "-----BEGIN PRIVATE KEY-----\n..."
)

if success:
    print("TLS certificate successfully set.")
else:
    print("Failed to set TLS certificate.")
```


### run
```python  
from webui import webui

my_window = webui.Window()

my_window.run("alert('Hello');")  # Run an alert in the web UI
```


### script
```python  
from webui import webui

my_window = webui.Window()

result = my_window.script("return 4 + 6;")
if result.error:
    print("JavaScript execution failed.")
else:
    print(f"JavaScript result: {result.response}")
```


### set_runtime
```python  
from webui import webui

my_window = webui.Window()

my_window.set_runtime(webui.Runtime.Bun)  # Use Bun as the JavaScript/TypeScript runtime
```


### get_count
```python  
from webui import webui

def callback(e: webui.Event):
    count = e.get_count()
    print(f"The event has {count} arguments.")
```


### get_int_at
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_int_at(0)
    print(f"The integer at index 0 is {value}.")
```


### get_int
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_int()
    print(f"The first argument is {value}.")
```


### get_float_at
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_float_at(0)
    print(f"The float at index 0 is {value}.")
```


### get_float
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_float()
    print(f"The first argument as a float is {value}.")
```


### get_string_at
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_string_at(0)
    print(f"The string at index 0 is '{value}'.")
```


### get_string
```python  
from webui import webui

def callback(e: webui.Event):
    value = e.get_string()
    print(f"The first argument as a string is '{value}'.")
```


### get_bool_at
```python  
from webui import webui

def callback(e: webui.Event):
    is_valid = e.get_bool_at(0)
    print(f"The boolean value at index 0 is {is_valid}.")
```


### get_bool
```python  
from webui import webui

def callback(e: webui.Event):
    is_valid = e.get_bool()
    print(f"The first argument as a boolean is {is_valid}.")
```


### get_size_at
```python  
from webui import webui

def callback(e: webui.Event):
    arg_size = e.get_size_at(0)
    print(f"The size of the argument at index 0 is {arg_size} bytes.")
```


### get_size
```python  
from webui import webui

def callback(e: webui.Event):
    arg_size = e.get_size()
    print(f"The size of the first argument is {arg_size} bytes.")
```


### return_int
```python  
from webui import webui

def callback(e: webui.Event):
    e.return_int(123)
```


### return_float
```python  
from webui import webui

def callback(e: webui.Event):
    e.return_float(123.456)
```


### return_string
```python  
from webui import webui

def callback(e: webui.Event):
    e.return_string("Response...")
```


### return_bool
```python  
from webui import webui

def callback(e: webui.Event):
    e.return_bool(True)
```


### open_url
```python  
from webui import webui

webui.open_url("https://webui.me")  # Open the WebUI website in the default browser
```


### start_server
```python  
from webui import webui

my_window = webui.Window()

url = my_window.start_server("/full/root/path")
print(f"Server started at: {url}")
```


### get_mime_type
```python  
from webui import webui

mime_type = webui.get_mime_type("foo.png")
print(f"MIME type: {mime_type}")  # Output: image/png
```


### get_port
```python  
from webui import webui

my_window = webui.Window()

port = my_window.get_port()
print(f"WebUI is running on port: {port}")
```


### get_free_port
```python  
from webui import webui

port = webui.get_free_port()
print(f"Available port: {port}")
```

