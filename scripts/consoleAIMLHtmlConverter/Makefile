#
# Simple makefile to illustrate
# how to build a project using RebeccaAIML
#

#
# Where you installed the distribution
#
prefix=/usr/local


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
# Where the rebecca shared object and
# executable is to go
#
REBECCA_LIB=/usr/local/lib

#
# Where to output the sample
#
REBECCA_OUTPUT=/usr/local/share/librebecca/bin

#
# List of all the objects 
# that are to go into the shared object
#
#
SHARED_OBJS=CustomAIML.o\
	        CustomTagsImpl.o\
			CustomTopic.o\
			Html.o\
			InnerTemplateAIMLTags.o\
			Links.o\
			sanitizeString.o\
			WebPage.o

all: ${REBECCA_LIB}/libcustomHtmlTagLayer.so ${REBECCA_OUTPUT}/consoleAIMLHtmlConverter

${REBECCA_LIB}/libcustomHtmlTagLayer.so: ${SHARED_OBJS} 
	${CXX} -shared -Wl,-soname,libcustomHtmlTagLayer.so -o ${REBECCA_LIB}/libcustomHtmlTagLayer.so ${SHARED_OBJS}

CustomAIML.o: CustomAIML.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC CustomAIML.cpp

CustomTagsImpl.o: CustomTagsImpl.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC CustomTagsImpl.cpp

CustomTopic.o: CustomTopic.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC CustomTopic.cpp

Html.o: Html.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC Html.cpp

InnerTemplateAIMLTags.o: InnerTemplateAIMLTags.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC InnerTemplateAIMLTags.cpp

Links.o: Links.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC Links.cpp

sanitizeString.o: sanitizeString.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC sanitizeString.cpp

WebPage.o: WebPage.cpp
	${CXX} -I${REBECCA_INCLUDES} -c -fPIC WebPage.cpp

${REBECCA_OUTPUT}/consoleAIMLHtmlConverter: consoleAIMLHtmlConverter.o
	${CXX} -o ${REBECCA_OUTPUT}/consoleAIMLHtmlConverter consoleAIMLHtmlConverter.o -L${REBECCA_LIB} -lrebecca-mt -Wl,-rpath=${REBECCA_LIB}

consoleAIMLHtmlConverter.o: consoleAIMLHtmlConverter.cpp
	${CXX} -I${REBECCA_INCLUDES} -c consoleAIMLHtmlConverter.cpp 

clean:
	-rm ${SHARED_OBJS}
	-rm ${REBECCA_LIB}/libcustomHtmlTagLayer.so
	-rm ${REBECCA_OUTPUT}/consoleAIMLHtmlConverter

