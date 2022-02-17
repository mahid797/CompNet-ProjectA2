JFLAGS = -g
JC = javac
JARFILE = DNSLookup.jar
SRC = $(shell find src -iname '*.java')
BIN = out/production/DNSLookupProcess
all: $(JARFILE)

.SUFFIXES: .java .class
$(BIN)/%.class: $(SRC)
	mkdir -p $(BIN)/
	$(JC) -sourcepath src -d $(BIN)/ $(JFLAGS) src/$*.java

$(JARFILE): $(BIN)/ca/yorku/eecs/dnslookup/DNSLookupCUI.class
	jar cvfe $(JARFILE) ca.yorku.eecs.dnslookup.DNSLookupCUI -C $(BIN) ca/

run: $(JARFILE)
	java -jar $(JARFILE)

clean:
	-rm -rf  $(JARFILE) $(BIN)/*
