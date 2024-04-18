RENDER = prman
FILE = rubicsCube
VIEWER = sho

all : ${FILE}.tiff
	${VIEWER} ${FILE}.tiff

${FILE}.tiff : ${FILE}.rib
	${RENDER} ${FILE}.rib

clean :
	rm -f *.tiff

	