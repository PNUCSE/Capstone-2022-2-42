CC=gcc
CPC=g++
tensorflow=-ltensorflow
filename=model_3class

runc: ${filename}.c 
	${CC} ${filename}.c ${tensorflow} -o ${filename}

runcpp: ${filename}.cpp 
	${CPC} ${filename}.cpp ${tensorflow} -o ${filename}

clean: 
	rm -f ${filename}