#
# Simple makefile to illustrate 
# how to build a project using RebeccaAIML
#

#
# Where you installed the distribution
#
prefix=/usr/local 

#
# Where you wanted the the lib
# to be located.  This is usually
# the same place as the prefix.
#
exec_prefix=/usr/local

#
# Where the rebecca includes are
#
REBECCA_INCLUDES=/usr/local/include

#
# Where the rebecca shared object is 
#
REBECCA_LIB=/usr/local/lib

#
# Where to output the sample
#
REBECCA_OUTPUT=/usr/local/share/librebecca/bin


${REBECCA_OUTPUT}/console-network: console-network.o
	${CXX} -o ${REBECCA_OUTPUT}/console-network console-network.o -L${REBECCA_LIB} -lrebecca-network -Wl,-rpath=${REBECCA_LIB}

console-network.o: console-network.cpp
	${CXX} -I${REBECCA_INCLUDES} -c console-network.cpp


clean:
	-rm console.o	
	-rm ${REBECCA_OUTPUT}/console-network
