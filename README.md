# ARP_second_assignment

## Project made by:

Claudio Tomaiuolo S5630055

Barış Aker S5430437

## ncurses library installation
To install the ncurses library, simply open a terminal and type the following command:
```console
sudo apt-get install libncurses-dev
```
## libbitmap library installation
Download this repository : `https://github.com/draekko/libbitmap`.
Navigate to the root directory of the folder in the console and run the following commands.
For making the configuration
```console
./configure 
```

For compiling
```console
make
```

For installing
```console
sudo make install
```

After the installation, check if the library has been installed navigating to `/usr/local/lib`, where you are supposed to find the `libbmp.so` file.

The last step is to open the `.bashrc` into the terminal:
```console
nano .bashrc
```
and add `export LD_LIBRARY_PATH="/usr/local/lib:$LD_LIBRARY_PATH"`.
Now reload your `.bashrc`:
```console
source .bashrc
```

## Run the code
Navigate to root directory of the project.
For compiling, run:
```console
./compile.sh
```
Then, run:
```console
./run.sh
```

## Explaination 

The aim of the Project to creating to separated programs which are in communication with the shared memory. 

In the the src folder there are three main files, one of them is processA, the other one is processB and the last file is the master file. 

When the user will run the program they need to see two consoles, processA and processB. The user should control the object which is inside of the processA by using the right, left, upper and down buttons on the keyboard. Depends on these user inputs the object will be move on the processA console. On the processA console there is P button for printing the image and when the user will push that button image will be save to the .bmp file. During these processes happening the user can follow the object’s entire movement with the 0’s on processB window. On the processB window all the movement can be seen as a real time and the previous movements will not be disappear that is why all movements can be visible. The processA and processB are in connection with the shared memory by using semaphores. 

In the processA bmp files sizes had been set, semaphores and circle drawing and cancelling functions had been created. Depends on to the inputs which are given by the user the movement of the object had been provided inside of the infite while loop. At the end of the processA the semaphoers had been closed and unlinked, bmp file had been destroyed and the log file had been closed. 

In the processB also bmp files sizes had been set, semaphores and circle drawing and cancelling functions had been created. At the end of the processA the semaphoers had been closed and unlinked, bmp file had been destroyed and the log file had been closed. 

Inside of the master file there is child process creation, processA and processB console creations and the function to write to the log file had been done. 
