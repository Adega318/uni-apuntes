# Rango dinámico
Rango entre el valor de iluminación menor y el mayor nivel de iluminación que el medio puede representar.
## HDR
Sistema de combinación de imágenes basado en una ponderación de diferentes fotografías con bajo rango dinámico para obtener una nueva fotografía con alto rango dinámico.
# Luz monocroma
## Halftoning
Técnica basada en la integración del sistema de visión humana que permite que él suso de puntos cercanos represente una imagen coherente.
# Color (No lo suele preguntar)
# Sombreado de polígonos
## Sombreado plano
Se calcula el sombreado para un punto del objeto y se aplica dicho sombreado sobre todos los puntos, este sombreado es deficiente en superficies no perpendiculares a la normal o de tamaño apreciable.
## Sombreado interpolativo
Se calcula el color por los vértices y se interpola a lo largo de las aristas. Este sistema tiene problemas cuando la luz da directamente en una unión de aristas lo que produce Bandas de Mach.
## Sombreado de Phong
Se hace el cálculo de las normales a lo largo de toda la arista, esto elimina las Bandas de Mach en gran medida.
# Sombras
El sombreado se puede hacer mediante la toma de la luz como un punto de proyección, usado para proyectar los bordes del objeto sobre el fondo dando lugar a sombras duras con los problemas de la incapacidad de interacción de las sobras sobre otros objetos o sobre sí mismo.
## Volúmenes de sombra
Se crea un polígono infinito sobre cada objeto en dirección opuesta a la luz, cuando un objeto interseca este volumen la parte intersecada se encuentra a la sombra. Este cálculo se hace con la suma y resta a un contador por el uso de caras entrantes y salientes.
## DSV
Sistema de detección de superficies visibles basado en la eliminación de los polígonos no visibles por la luz y la intersección de este recorte con el objeto original para sombrearlo.
## Z-Buffer
Se calculan los puntos más cercanos desde el punto de vista de la luz haciendo uso de las técnicas de z-buffer, a estas coordenadas desde el punto de vista de la luz se le llama mapa de sombreado, con esta información se sombrea desde el punto de vista normal. Este método tiene errores de precisión por la transformada de las coordenadas y problemas de aliasing ya presente en el sistema de z-buffer original.
# Texturas
## Mapeado indirecto 
### Algoritmos de mapeado (NO ENTRA)