
#FC  = gfortran
FC  = ifort
#FFLAGS := -I$(INC_NETCDF) -L$(LIB_NETCDF) -lnetcdff -lnetcdf -g -fbacktrace -fcheck=all -DSCMDIAG 
#FFLAGS := -I$(INC_NETCDF) -L$(LIB_NETCDF) -lnetcdff -lnetcdf -fcheck=all -fbacktrace
FFLAGS := -I$(INC_NETCDF) -L$(LIB_NETCDF) -lnetcdff -lnetcdf -DSCMDIAG

VPATH = ../src

SRC = scmdiag.f90 conv_jp.F90


OBJ = $(addsuffix .o, $(basename $(SRC)))

all: main

main: $(OBJ) main.o
	$(FC) $(FFLAGS) $(OBJ) main.o -o $@

%.o : %.F90
	$(FC) $(FFLAGS) -c $<

%.o : %.f90
	$(FC) $(FFLAGS) -c $<

clean:
	rm *.o *.mod

#dependence

conv_jp.o : scmdiag.o

