CFLAGS=-Wall -pedantic -g -DUSCSI_SCSIPI -DSCSI -I/usr/pkg/include
LDFLAGS=-Wl,-R/usr/pkg/lib -L/usr/pkg/lib -lgc

all : mamtool

mamtool : endian_utils.o mamtool.o uscsi_subr.o uscsi_sense.o
	$(CC) $(LDFLAGS) -o $@ endian_utils.o uscsi_sense.o mamtool.o uscsi_subr.o

%.o : %.c *.h
	$(CC) $(CFLAGS) -c $<

clean :
	rm -f *.o
	rm -f mamtool

