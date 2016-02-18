bin_path := bin
lib_path := lib/

c_flags         := -g -fPIC -DDEBUG -DGCC -DX86_64
o_flags         := -g -fPIC -lpthread

target := $(bin_path)/server

c_flags := $(c_flags) 
o_flags := $(o_flags) /usr/local/lib/libevent.a -lrt

c_srcs:= \
        echoserver.c\
        workqueue.c 

cpp_srcs :=


objs   := $(patsubst %.cpp,%.o,$(cpp_srcs)) $(patsubst %.c,%.o,$(c_srcs))

all:$(target)



$(target):$(objs)
	g++ -o $@ $(objs) $(o_flags) 

%.o:%.cpp
	g++ -c -o $@ $< $(c_flags)

%.o:%.c
	gcc -c -o $@ $< $(c_flags)

clean:
	rm $(objs)
	rm $(target)
                                                  
