HOMEL=$(PWD)
TOP=../bin
## binary for install  
# DEBUG_OPTIONS= -g -pg
##DEBUG_OPTIONS= -g 
BIN=$(HOMEL)/../bin
PERLDIR=$(HOMEL)/perlsrc

NLIB=$(HOMEL)/admixlib/nicklib.a
IDIR=$(HOMEL)/admixinclude

VPATH=.:nicksrc
DEBUG_OPTIONS= -g 

CFLAGS= -c -g -p -I$(IDIR) -Wimplicit
FORTRAN_LIB=ifcore

OBJ=strsubs.o sortit.o vsubs.o statsubs.o linsubs.o getpars.o xsearch.o gauss.o	gds.o
##TWTAB=\"$(HOMEL)/admixtables/twtable\"

statsubs.o:     tables	nicksrc/statsubs.c
	$(CC)  $(CFLAGS) -o statsubs.o nicksrc/statsubs.c

QCC = -Wl,-Bdynamic -mkl -lgsl -Wl,-Bstatic -Wl,-Bdynamic -l$(FORTRAN_LIB) -lm 

T2=dowtjack
T20=dowtjack.o

M1=qpDstat 
M1O=qpDstat.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M2=qp3Pop 
M2O=qp3Pop.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M3=qpF4ratio  
M3O=qpF4ratio.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M4=rolloff  
M4O=rolloff.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M5=qpBound  
M5O=qpBound.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M6=qpdslow 
M6O=qpdslow.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M6B=qpdweight 
M6BO=qpdweight.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
M7=qpwest 
M7O=qpwest.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o

M8=qpAdm  
M8O=qpAdm.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o  f4rank.o  eigsubs.o eigx.o
 
M9=qpWave  
M9O=qpWave.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o  f4rank.o  eigsubs.o eigx.o
## was qp4wave2
 
 
M2=qp3Pop 
X1=convertf  
X1O=convertf.o  mcio.o  admutils.o  egsubs.o h2d.o  exclude.o

X2=grabpars  
X2O=grabpars.o 

X3=contam1 
X3O=contam1.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o
 
X4=mksamp1  
X4O=mksamp1.o  qpsubs.o mcio.o  admutils.o  egsubs.o h2d.o  exclude.o regsubs.o  

X5=qpff3base 
X5O=qpff3base.o qpgsubs.o qpsubs.o mcio.o admutils.o egsubs.o regsubs.o  ldsubs.o

X6=qpginv
X6O=qpginv.o qpgsubs.o qpsubs.o mcio.o admutils.o egsubs.o regsubs.o  ldsubs.o 

expfit.sh:	expfit.templ
	sed -e "s&BBBIN&$(BIN)&" < expfit.templ > expfit.sh
	chmod +x expfit.sh
 
IDIR=$(HOMEL)/admixinclude  
##ISTR= -I$(HOME)/include  -I/opt/nag/libC/include


$(M1): nicklib	$(M1O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M1) $(M1O) $(NLIB) -lm  

$(M6): nicklib	$(M6O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M6) $(M6O) $(NLIB) -lm

$(M6B): nicklib	$(M6BO)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M6B) $(M6BO) $(NLIB) -lm

$(M7): nicklib	$(M7O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M7) $(M7O) $(NLIB) -lm


$(T2): nicklib $(T20)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(T2) $(T20) $(NLIB) -lm



$(M2): nicklib	$(M2O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M2) $(M2O) $(NLIB) -lm

$(M3): nicklib	$(M3O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M3) $(M3O) $(NLIB) -lm

$(M4): nicklib	$(M4O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M4) $(M4O) $(NLIB) -lm

$(M5): nicklib	$(M5O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M5) $(M5O) $(NLIB) -lm

$(X1): nicklib	$(X1O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X1) $(X1O) $(NLIB) -lm

$(X2): nicklib	$(X2O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X2) $(X2O) $(NLIB) -lm

$(X4): nicklib	$(X4O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X4) $(X4O) $(NLIB) -lm

$(X5): nicklib	$(X5O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X5) $(X5O) $(NLIB) -lm

$(X6): nicklib	$(X6O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X6) $(X6O) $(NLIB) -lm


$(M8): nicklib	$(M8O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M8) -fopenmp $(M8O) $(NLIB) $(QCC) 

$(M9): nicklib	$(M9O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M9) -fopenmp $(M9O) $(NLIB) $(QCC) 



PROGS= qp3Pop qpDstat qpF4ratio qpAdm qpWave rolloff convertf dowtjack expfit.sh grabpars qpBound qpGraph
PROGS2 = rexpfit.r  wtjack.pl 

all: nicklib $(PROGS) 

install:	all	tables
	mkdir -p $(TOP)
	cp $(PROGS) $(TOP)
	cp $(PROGS2) $(TOP)

uninstall:
	rm -f $(NLIB) tables
	rm -f $(TOP)/*



libnick.a:	dirs tables  $(OBJ)
	ar -r libnick.a $(OBJ)
	ranlib libnick.a

nicklib:	dirs  tables  libnick.a 
	cp libnick.a  $(NLIB)


tables:    
	echo "tables made"  > tables
	cp twtable  $(HOMEL)/admixtables
	
dirs:	
	mkdir -p  $(HOMEL)/admixlib
	mkdir -p  $(HOMEL)/admixtables
	mkdir -p  $(HOMEL)/admixinclude
	mkdir -p  $(BIN)
	cp  *.h  $(IDIR)
	cp  nicksrc/*.h  $(IDIR)

clean: 
	rm -f *.o 
	rm -f *junk*
	rm -f core
	rm -f libnick.a
	rm -f $(PROGS)
	rm -f nicksrc/*.o

clobber: clean rmdirs uninstall


rmdirs: 
	rm -rf $(HOMEL)/admixlib 
	rm -rf $(HOMEL)/admixtables 
	rm -rf $(HOMEL)/admixinclude 

ISTR= -I$(HOMEL)/admixinclude  
CFLAGS= -c -g -p $(ISTR) -Wimplicit-int

## gsl-config may help here

M9F2=qpGraph 
M9F2O=qpGraph.o  gslqp.o qpgsubs.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o

M9G=qpreroot 
M9GO=qpreroot.o qpgsubs.o qpsubs.o mcio.o ldsubs.o admutils.o  egsubs.o regsubs.o


$(M9F2): nicklib $(M9F2O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(M9F2) $(M9F2O) $(NLIB) -mkl -lgsl -lm 

$(M9G): $(M9GO)
	$(CC) -I$(IDIR)  $(DEBUG_OPTIONS) -o $(M9G) $(M9GO) $(NLIB) -lm 

$(X3): nicklib	$(X3O)
	$(CC) -I$(IDIR) $(DEBUG_OPTIONS) -o $(X3) $(X3O) $(NLIB) -lm 

