# Apuntes Estadística, LAB 1 ejercicio 2

```matlab
X = randi([6, 48], 100, 1); % Genera 100 números aleatorios enteros entre 6 y 50.

R = max(X) - min(X); % Rango
K = 1 + 3.3*log(length(X)); % Cantidad de intervalos
L = round(R / K); % Longitud de intervalos

intervalos = min(X):L:max(X); % Definir los límites de los intervalos
[fi, edges] = histcounts(X, intervalos); % Agrupar los datos en los intervalos y obtener las frecuencias absolutas

marca_clase = (edges(1:end-1) + edges(2:end)) / 2; % Calcular la marca de clase representativa (promedio de los límites de cada intervalo)
xi = fi / numel(X); % Calcular la frecuencia relativa

% Crear los intervalos como texto para la tabla
intervalos_texto = arrayfun(@(a,b) sprintf('[%d, %d)', a, b), edges(1:end-1), edges(2:end), 'UniformOutput', false);

% Crear una tabla con los intervalos, marca de clase, frecuencias absolutas y relativas
tabla_frecuencias = table(intervalos_texto', marca_clase', fi', xi', 'VariableNames', {'Intervalo', 'Marca de Clase', 'Frecuencia Absoluta', 'Frecuencia Relativa'});

disp(tabla_frecuencias)