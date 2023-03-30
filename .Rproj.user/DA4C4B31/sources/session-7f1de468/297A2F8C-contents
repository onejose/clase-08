## clase-05: leer/escribir conjuntos de datos
## update: 11-11-2021
## R version 4.1.1 (2021-08-10)

## limpiar entorno
rm(list=ls()) 

## instalar/llamar pacman
require(pacman)

## usar la función p_load de pacman para instalar/llamar las librerías de la clase
p_load(rio, # función import/export: permite leer/escribir archivos desde diferentes formatos. 
       skimr, # funcion skim: describe un conjunto de datos
       janitor) # contiene conjuntos de datos.
     
## verificar directorio
getwd()
list.files()

## tidyverse
install.packages(tidyverse)
library("tidyverse")

## **[2.] Adicionar variables a un conjunto de datos**


### **2.1 Conjuntos de datos disponibles en la memoria de R**
data(package="datasets")

db=import("input/geih_2021.xlsx")
db=import(file = "input/geih_2021.xlsx")

### **2.2 Función `$`**

db$constante = 1
#asi r genera un vector de 1 para todas las observaciones

db$ingreso_min= db$ing_laboral/960000

### **2.3 mutate()** esta es funcion de dplyr

db = mutate(.data=db , ing_edad = ing_laboral/edad)
db=mutate(.data= db , ing_edad2 = ingreso_min/edad)

### **2.4 Generar variables usando condicionales:**

# data$var

db$mayor_edad =ifelse(test = db$edad>=18, yes=1, no = 0)

# mutate

db=mutate(.data=db , mayor_edad_2=ifelse(test = edad>=18, yes=1, no =0))
db=mutate(db, edad_mujer=ifelse(edad>=18 & mujer==1, yes=1, no = 0),
          mujer_urbana=ifelse(test=mujer==1 & urbano==1 , yes=1, no=0))

db$edad_mujer =ifelse(test = db$edad>=18 & db$mujer==1, yes=1, no = 0)
db$mujer_urbana =ifelse(test = db$mujer==1 & db$urbano==1, yes=1, no = 0)




### **2.5 Aplicar funciones a variables**


#### **Ordenar un objeto por os valores de una variable:**

mean (c(1,2,3,NA))
db$edad_solo_mujer=ifelse(db$mujer==1, yes=db$edad, no=NA)

db$promedio_edad_mujer = mean(db$edad_solo_mujer, na.rm=T)

## **[3.] Remover filas y/o columnas**
  
### **3.1 Seleccionar variables**
  


#### **3.1.1 Seleccionar variables usando partes del nombre**
db$secuencia_p= NULL
db_34=select(db,-hogar)
db_31=select(db,edad,mujer)
db_ing=select(db, directorio, starts_with('ing'))
db_a=select(db, ends_with("a"))

#### **3.1.2 Seleccionar variables usando el tipo**


#### **3.1.3 Seleccionar variables usando un vector**


#### **3.1.4 Deseleccionar variables**


  ### **3.2 Remover filas/observaciones**

db_solo_mujer1=subset(x=db, mujer==1)
db_solo_mujer2=subset(x=db, mujer!=0)
db_superio_media=subset(x=db, nivel_educacion=="superior" | nivel_educacion=="media")

db_solo_mujer1=
#### **3.2.1 Remover filas usando condicionales**

## **Para seguir leyendo:**
  
#  * Wickham, Hadley and Grolemund, Garrett, 2017. R for Data Science 
browseURL("https://r4ds.had.co.nz")

# + Cap. 5: Data transformation
# + Cap. 10: Tibbles
# + Cap. 12: Tidy data

