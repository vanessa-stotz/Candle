RENDER=prman
FILE=candle
SLCOMPILER=oslc
VIEWER=sho
SLEXT=oso

SHADERNAMEWAXS=waxSurface
SHADERNAMEWAXD=waxDisplacement
SHADERNAMEWICKS=wickSurface
SHADERNAMEWICKD=wickDisplacement
SHADERNAMEWALL=wall


all : ${FILE}.tiff
	${VIEWER} ${FILE}.tiff

${SHADERNAMEWAXS}.${SLEXT} : ${SHADERNAMEWAXS}.osl
	${SLCOMPILER} ${SHADERNAMEWAXS}.osl

${SHADERNAMEWAXD}.${SLEXT} : ${SHADERNAMEWAXD}.osl
	${SLCOMPILER} ${SHADERNAMEWAXD}.osl

${SHADERNAMEWICKS}.${SLEXT} : ${SHADERNAMEWICKS}.osl
	${SLCOMPILER} ${SHADERNAMEWICKS}.osl

${SHADERNAMEWICKD}.${SLEXT} : ${SHADERNAMEWICKD}.osl
	${SLCOMPILER} ${SHADERNAMEWICKD}.osl

${SHADERNAMEWALL}.${SLEXT} : ${SHADERNAMEWALL}.osl
	${SLCOMPILER} ${SHADERNAMEWALL}.osl

${FILE}.tiff : ${SHADERNAMEWAXS}.${SLEXT} ${SHADERNAMEWAXD}.${SLEXT} ${SHADERNAMEWICKS}.${SLEXT} ${SHADERNAMEWICKD}.${SLEXT} ${SHADERNAMEWALL}.${SLEXT} ${FILE}.rib
	cat ${FILE}.rib | sed s/XXXX/${SHADERNAMEWAXS}/g | ${RENDER}

clean :
	rm -f *.tiff *.${SLEXT}
