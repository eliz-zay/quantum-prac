.PHONY: all init test report report_inn clean
all: init test clean
polus: init_polus test clean
report: init report_inn clean
init:
	rm -f time.csv
	clang++ -Xpreprocessor -fopenmp main.cpp -o main -lomp
init_polus:
	rm -f time.csv
	xlc++ -qsmp=omp -fopenmp main.cpp -o main
test:
	./main $(arg1) $(arg2) $(arg3)
report_inn:
	python test.py
clean:
	rm ./main