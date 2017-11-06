TARGET = TL2-Pepe-Verstraeten.pdf
OUT_FORMAT = latex
IN_FORMAT = markdown
HEADER = header.tex
TEMPLATE = fiuba-template.latex

.PHONY: all clean

all: $(TARGET)

$(TARGET): *.yaml *.md
	pandoc -H $(HEADER) -f $(IN_FORMAT) -t $(OUT_FORMAT) -s --template $(TEMPLATE) -o $(TARGET) $^

clean:
	-@rm -f $(TARGET)
