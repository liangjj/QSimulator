CC = g++
#CFLAGS += -pg
CFLAGS += -O3 -ffast-math
CFLAGS += -march=native
CFLAGS += -Wall
INC_DIR += /opt/include/
LIB_DIR += /opt/lib
LIBS += -lcvm_em64t -loptions -lmathexpr -lfftw3
all : qsimu

qsimu : gpe3D.o gpe2D.o gpe1D.o thermal.o gpe.o main.o 
	$(CC) $(CFLAGS) -I$(INC_DIR) -L$(LIB_DIR) $^ -o $@ $(LIBS) && mv $@ ../bin/

gpe3D.o gpe2D.o gpe1D.o thermal.o gpe.o main.o : %.o : %.cpp
	$(CC) $(CFLAGS) -I$(INC_DIR) -c $<

clean :
	rm -rf *.o
