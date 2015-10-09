# $< is input.
# $@ is output.

GRAPHS = $(wildcard graphs/*.dot)
IMAGES = $(patsubst graphs/%.dot,img/%.png,$(GRAPHS))

all: $(IMAGES) answers.pdf

img/%.png: graphs/%.dot
	mkdir -p img
	dot -T png $< -o $@

answers.pdf: answers.md $(IMAGES)
	pandoc --smart --standalone --highlight-style=haddock -f markdown -t latex -o $@ $<

clean:
	rm -rf img
	rm answers.pdf
