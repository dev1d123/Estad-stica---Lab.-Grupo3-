# Apuntes Estadística, LAB 1


Los comandos en MATLAB realizan lo siguiente:

1. **`X = randi([6, 50], 100, 1)`**: Genera 1000 números aleatorios enteros entre 6 y 50.
2. **`XI = sort(unique(X))`**: Ordena y obtiene los valores únicos de `X`.
3. **`FI = hist(X, XI)`**: Cuenta cuántas veces aparece cada valor en `XI` dentro de `X`.
4. **`numel(find(X == 21))`**: Cuenta cuántas veces aparece el número 21 en `X`.
6. **`HI = FI/numel(X)`**: Calcula las frecuencias relativas de los valores en `X`.
7. **`TB_table = array2table(TB, 'VariableNames', {'XI', 'FI', 'HI'})`**: Crea una tabla con los valores únicos, sus frecuencias absolutas y relativas.
8. **`disp(TB_table)`**: Muestra la tabla en pantalla.
