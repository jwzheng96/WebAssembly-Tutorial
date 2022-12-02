# WebAssembly-Tutoriail

## Compiling from C/C++ to WebAssembly

1、create a c file(hello.c)

```c
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

2、install the Emscripten compiler environment

```bash
# Get the emsdk repo
git clone https://github.com/emscripten-core/emsdk.git

# Enter that directory
cd emsdk

# Fetch the latest version of the emsdk (not needed the first time you clone)
git pull

# Download and install the latest SDK tools.
./emsdk install latest

# Make the "latest" SDK "active" for the current user. (writes .emscripten file)
./emsdk activate latest

# Activate PATH and other environment variables in the current terminal
source ./emsdk_env.sh
```

3、running the example

```bash
#  If you try to open generated HTML file (hello.html) directly from your local hard drive (e.g. file://your_path/hello.html), you will end up with an error message along the lines of both async and sync fetching of the wasm failed. You need to run your HTML file through an HTTP server (http://)

#set up a local testing server
# If Python version returned above is 3.X
# On Windows, try "python -m http.server" or "py -3 -m http.server"
python3 -m http.server
# If Python version returned above is 2.X
python -m SimpleHTTPServer

# By default, this will run the contents of the directory on a local web server, on port 8000. You can go to this server by going to the URL localhost:8000 in your web browser. Here you'll see the contents of the directory listed — click the HTML file you want to run.
```


