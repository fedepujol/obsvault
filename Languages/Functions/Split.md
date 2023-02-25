# Procedure Split
Para un string de tamaño indeterminado. Primero se tiene que definir el tamaño del array a devolver con ArraySize.

## Parametros de entrada
pString -> Character (palabra a cortart)
pRegex -> Character (patron por el cual se aplica el corte)
## Parametros de Salida
pArray -> Character (arreglo donde estan los cortes)
pError -> Logical (variable que indica si hubo algun error en el proceso)

```
PROCEDURE Split:
	DEFINE INPUT   PARAMETER pString AS CHARACTER.
	DEFINE INPUT   PARAMETER pRegex AS CHARACTER.
	DEFINE OUTPUT  PARAMETER pArray AS CHARACTER EXTENT.
	DEFINE OUTPUT  PARAMETER pError AS LOGICAL INITIAL NO.
	DEFINE VARIABLE i AS INTEGER NO-UNDO.
	DEFINE VARIABLE arraySize AS INTEGER NO-UNDO.
	DEFINE VARIABLE j AS INTEGER NO-UNDO INITIAL 1.

	IF pRegex EQ ? OR pRegex EQ "" THEN 
		pRegex = " ".
	IF LENGTH(pString) EQ 0 OR pString EQ ? THEN 
		pError = YES.

	RUN ArraySize(INPUT pString, INPUT pRegex, OUTPUT arraySize). 
	EXTENT(pArray) = arraySize.

	REPEAT i = 1 TO LENGTH(pString):
		IF SUBSTRING(pString, i, 1) EQ pRegex THEN
			j = j + 1.
		ELSE
			pArray[j] = pArray[j] + SUBSTRING(pString, i, 1).
	END.

END PROCEDURE.

PROCEDURE ArraySize:
	DEFINE INPUT PARAMETER pString AS CHARACTER.
	DEFINE INPUT PARAMETER pRegex AS CHARACTER.
	DEFINE OUTPUT PARAMETER arraySize AS INTEGER INITIAL 1.

	DEFINE VARIABLE i AS INTEGER     NO-UNDO.

	REPEAT i = 1 TO LENGTH(pString):
		IF SUBSTRING(pString, i, 1) EQ pRegex THEN
			arraySize = arraySize + 1.
	END.

END PROCEDURE.
```