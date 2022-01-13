# ejercicio_1102.sh
##Exercise 1.10.4 on Buzzard et al. (2016)
1. ¿Cuántas veces se registraron los niveles de los individuos 3 y 27?
Primero se revisa la estructura del archivo
$head -n 3 Gesquiere2011_data.csv
Luego se extrae todas las columnas que contengan un 3 (o 27) y se la cuenta
$cut -f 1 Gesquiere2011_data.csv | grep -c -w 3
Se recurre al mismo comando para 27
$cut -f 1 Gesquiere2011_data.csv | grep -c -w 27
