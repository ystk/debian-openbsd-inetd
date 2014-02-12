--- /dev/null
+++ b/Makefile.debian
@@ -0,0 +1,20 @@
+CFLAGS ?= -g -O2
+
+DEFS := -DLIBWRAP
+LIBS := -lwrap
+
+CPPFLAGS += $(DEFS)
+
+inetd_OBJECTS := inetd.o setproctitle.o strlcpy.o bsd-closefrom.o
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
+	rm -f inetd inetd.o setproctitle.o strlcpy.o
+
