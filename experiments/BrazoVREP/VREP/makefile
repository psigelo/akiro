CFLAGS = -I./remoteApi -I./include -DNON_MATLAB_PARSING -DMAX_EXT_API_CONNECTIONS=255
LDFLAGS = -lpthread

OBJS = ./remoteApi/extApi.o ./remoteApi/extApiPlatform.o 
OUTPUT = bin/bubbleRobClient

OS = $(shell uname -s)
ECHO = @

ifeq ($(OS), Linux)
	CFLAGS += -D__linux
else
	CFLAGS += -D__APPLE__
endif

all: $(OBJS)
		

%.o: %.cpp
		@echo "Compiling $< to $@"
		$(ECHO)$(CXX) $(CFLAGS) -c $< -o $@

%.o: %.c
		@echo "Compiling $< to $@" 
		$(ECHO)$(CC) $(CFLAGS) -c $< -o $@

clean:
		@rm -f $(OBJS) bin/bubbleRobClient