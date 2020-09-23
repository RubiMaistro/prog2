all:	clean fdl

fdl:	clean validate_bhax-textbook_fdl_hu bhax-textbook_fdl.pdf
	
bhax-textbook_fdl.pdf: bhax-textbook-fdl.xml bhax-textbook.xls
	dblatex bhax-textbook-fdl.xml -p bhax-textbook.xls
	
.PHONY: validate_bhax-textbook_fdl_hu
validate_bhax-textbook_fdl_hu:
	xmllint --xinclude bhax-textbook-fdl.xml --output output.xml
	xmllint --relaxng http://docbook.org/xml/5.0/rng/docbookxi.rng output.xml --noout
	rm -f output.xml	
	
.PHONY: clean
clean:
	rm -f bhax-textbook-fdl.pdf
