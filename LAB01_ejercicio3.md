
# Apuntes Estadística, LAB 1, Ejercicio 3

### 1.- Creación del arreglo de datos
Primero, se define el arreglo de celdas que contiene las mascotas que poseen un grupo de personas:

```matlab
A = {'Perro', 'Gato', 'Pájaro', 'Pez', 'Perro', 
     'Gato', 'Loro', 'Pez', 'Tortuga', 'Gato', 
     'Conejo', 'Perro', 'Hámster', 'Loro', 'Pájaro', 
     'Gato', 'Perro', 'Tortuga', 'Gato', 'Conejo'};
```

### 2.- Conversión del arreglo de celdas a vector de strings
Para poder trabajar más fácilmente con los datos, convertimos el arreglo de celdas en un vector de strings. Esto facilita el análisis posterior:

```matlab
A_vector = string(A(:));
```

### 3.- Aplicación de la función `tabulate`
La función `tabulate` nos permite contar la frecuencia de cada tipo de mascota en el vector. El resultado es una tabla que contiene la lista de valores únicos, la frecuencia absoluta y la frecuencia porcentual.

```matlab
TABLA = tabulate(A_vector);
```

### 4.- Interpretación de la tabla
La tabla generada tiene 3 columnas importantes:
- `TABLA(:, 1)` -> Lista de tipos de mascotas (marcas de clase)
- `TABLA(:, 2)` -> Frecuencia absoluta de cada mascota
- `TABLA(:, 3)` -> Frecuencia porcentual de cada mascota

### 5.- Conversión a matrices de datos numéricos
Los datos están en una matriz de celdas, por lo que se deben convertir a tipos de datos manejables (números y strings) para trabajar de forma eficiente:

```matlab
TB = [string(TABLA(:,1)), str2double(TABLA(:,2)), str2double(TABLA(:,3))];
```

### 6.- Conversión de frecuencia relativa porcentual a normal
Para obtener la frecuencia relativa en lugar de la porcentual, simplemente dividimos la columna de frecuencias porcentuales entre 100:

```matlab
frecuencia_relativa = TB(:,3) / 100;
```

### 7.- Generación de la tabla final
Finalmente, combinamos la información de marcas de clase, frecuencias absolutas y frecuencias relativas en una tabla:

```matlab
TB_FINAL = [TB(:,1), num2cell(TB(:,2)), num2cell(frecuencia_relativa)];
```

El resultado es la siguiente tabla:

| Mascota  | Frecuencia Absoluta | Frecuencia Relativa |
|----------|---------------------|---------------------|
| Perro    | 4                   | 0.20                |
| Gato     | 5                   | 0.25                |
| Conejo   | 2                   | 0.10                |
| Loro     | 2                   | 0.10                |
| Pájaro   | 2                   | 0.10                |
| Pez      | 2                   | 0.10                |
| Hámster  | 1                   | 0.05                |
| Tortuga  | 2                   | 0.10                |

---

