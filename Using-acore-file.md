Every once in a while when you are developing stuff some application might crash. This can be especially annoying with race conditions or other types of bugs that appear rarely and usually your are not debugging the application when they occur. For this purpose Linux has a feature calle coredump. A coredump can be created automatically if you enable it.

### Enable core dumps
This is simple. Just run `ulimit -c unlimited` to enable core dumps of unlimited size. The default is usually 0.

### Using core dumps
First you have to figure out which application caused the core dump. Usually the last line of the core dump file contains the name o the application:

     strings <corefilename> | tail -n 1

