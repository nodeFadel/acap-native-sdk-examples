PROG1	= vdo_larod_preprocessing
OBJS1	= $(PROG1).c imgprovider.c
PROGS	= $(PROG1)

PKGS = gio-2.0 vdostream gio-unix-2.0 liblarod

CFLAGS  += -Iinclude

LDFLAGS += -L./lib -Wl,-rpath,'$$ORIGIN/lib'

CFLAGS += $(shell PKG_CONFIG_PATH=$(PKG_CONFIG_PATH) pkg-config --cflags $(PKGS))
LDLIBS += $(shell PKG_CONFIG_PATH=$(PKG_CONFIG_PATH) pkg-config --libs $(PKGS))

CFLAGS += -Wall
# This example is based on larod version 2
CFLAGS += -DLAROD_API_VERSION_2

all: $(PROGS)

$(PROG1): $(OBJS1)
	$(CC) $(CFLAGS) $(LDFLAGS) $^ $(LDLIBS) -o $@

clean:
	rm -f $(PROGS) *.o *.eap lib/* include/*
