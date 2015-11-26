ALL_MD = $(shell find . -name "*.md")

md2html : 
	@for f in $(ALL_MD); do                                       \
	        target=$$(echo $$f | sed 's:\.md$$:.html:g');         \
	        target=$$(echo $$target | sed 's:^\./:../:g');        \
	        mkdir -p $$(dirname $$target);                        \
	        echo "" > $$target;                                   \
	        echo "<html>" >> $$target;                            \
	        markdown $$f >> $$target;                             \
	        echo "$$f --> $$target";                              \
	        echo "<html/>" >> $$target;                           \
	done



