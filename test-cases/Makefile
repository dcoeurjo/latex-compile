
# Warning: no spaces allows in dirnames
DIRS=$(sort $(wildcard [0-9]*-*))

default: test-all


help:
	@echo This is the test suite for latex-compile 
	@echo useful targets: test-all and clean-all

echo:
	@echo ${DIRS}

clean-all:
	@echo cleaning $(words ${DIRS}) test-cases.
	@for i in ${DIRS} ;\
	do\
	   echo cleaning $${i} ;\
	   cd "$$i" && latex-clean && make clean && cd ..;\
	done

test-all-nocolor:
	@echo running $(words ${DIRS}) test-cases. '(zero means "OK")'
	@for i in ${DIRS} ;\
	do\
	  make -s -C $$i test ;\
	done

test-all:
	@make -s test-all-nocolor | grep --color -E '.*: [^0].*|$$'


compile-all:
	@echo running $(words ${DIRS}) test-cases. '(zero means "OK")'
	@for i in ${DIRS} ;\
	do\
          echo compiling $${i} ;\
	  make -C $$i compile ;\
	done
