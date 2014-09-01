--- /dev/null
+++ b/Makefile.debian
@@ -0,0 +1,20 @@
+CFLAGS ?= -g -O2
+
+DEFS := -DLIBWRAP $(shell pkg-config --cflags libbsd-overlay)
+LIBS := -lwrap $(shell pkg-config --libs libbsd-overlay)
+
+CPPFLAGS += $(DEFS)
+
+inetd_OBJECTS := inetd.o
+
+all: inetd
+
+.c.o:
+	$(CC) $(CPPFLAGS) $(CFLAGS) -c $<
+
+inetd: $(inetd_OBJECTS)
+	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ $^ $(LIBS)
+
+clean:
+	rm -f inetd inetd.o
+
