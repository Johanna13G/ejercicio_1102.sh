# ejercicio_1102.sh
## Exercise 1.10.4 on Buzzard et al. (2016)

1. ¿Cuántas veces se registraron los niveles de los individuos 3 y 27?

Primero se revisa la estructura del archivo

head -n 3 Gesquiere2011_data.csv

Luego se extrae todas las columnas que contengan un 3 (o 27) y se la cuenta

cut -f 1 Gesquiere2011_data.csv | grep -c -w 3

Se recurre al mismo comando para 27

cut -f 1 Gesquiere2011_data.csv | grep -c -w 27

Se obtiene:

Para 3 = 61

Para 27 = 5

3. Escriba un script que devuelva el número de veces que se muestreó a cada individuo.

Para esto se utilizará el siguiente comando para guardar los datos en una lista

myIDS=`tail -n +2 ../data/Gesquiere2011_data.csv | cut -f 1 | sort -n | uniq`

Luego para mostrar el número de veces que se muestró a cada individuo se usó lo siguiente

for id in $myIDS
do
    mycounts=`bash count_baboons.sh ../data/Gesquiere2011_data.csv $id`
    echo "ID:" $id "counts:" $mycounts
done 

Se obtiene:

ID: 1 counts: 10

ID: 2 counts: 2

ID: 3 counts: 61

ID: 4 counts: 46

...


