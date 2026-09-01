<img src="hello_c_gtk.svg" alt="hello_c_gtk" width="120">

# Example of C GTK4 Crosscompile

# Requirements for Debian 12
```
sudo apt-get update
sudo apt-get install gcc-arm-linux-gnueabihf gcc-mingw-w64 git wget make libgtk-4-dev
```

# Usage
## Build Linux binary 
```
make linux 
```

## Build Windows GTK binary  with Docker
```
docker run --name hello_gtk  -it --rm  -v "$(pwd)":"/root/src"   myridia/fedora_cross_compile /bin/bash
./makewindows.sh
```



## To run the exe you maybe need the dll files, you can find in the fedora folder

packed as bin64.tar.gz 

### for win64
```
/usr/x86_64-w64-mingw32/sys-root/mingw/bin/
```


### for win32

packed as bin32.tar.gz 

```
/usr/i686-w64-mingw32/sys-root/mingw/bin/
```

