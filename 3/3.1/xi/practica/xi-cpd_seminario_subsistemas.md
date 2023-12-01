# Espacio físico
## Elementos
- Rack, armario de tamaño estandarizado para instalación de sistemas.
- Carga útil.
	- Servidor blade, servidores enfocados a la eficiencia en sistemas enrackables.
	- Cabinas de discos, estructura para la conexión de discos.
## Normativa
Para regir el espacio físico tenemos la normativa ANSI que estipula las características del espacio físico. Las principales consideraciones son:
- Doble acceso en calles separadas.
- Edificio exclusivo.
- Altura de techos de 3 o más metros.
- Muelle de carga y descarga.
- Ausencia de radiación electromagnética.
- Ubicación par encima de la fontanería del edificio.
- Sala sin ventanas.
## Certificación de CPD
- Tier I, 28.82 horas parado al año.
- Tier II, 22.68 horas parado al año.
- Tier III, 1.57 horas parado al año.
- Tier IV, 52 minutos parado al año.
# Cableado estructurado
Los racks son estructurados con pasillo de aire frío y aire caliente y disponibilidad de conexión.
## Conexión
- ToR, cada rack tiene su conexión y swich propios.
- EoR and MoR, primer y último rack de la fila, tienen swich y conexión directa, con el resto interconectado a ellos.
# Sistema de distribución eléctrica
Sobre los sistemas eléctricos debemos diferencial entre:
- Potencia útil, energía dirigida a la operación de las máquinas.
- Alimentación de soporte, potencia dirigida a subsistemas del cpd.
	- PUE, consumo absoluto $PUE=\frac{C\_Global}{C\_TI}$
	- DCiE, consumo proporcional $DCiE=\frac{C\_TI}{C\_Global}$
## Eficiencia
La carga de electricidad del cpd se divide en:
- Refrigerador 23%.
- Humidificador 3%.
- CRAC/CRAH 15%.
- TI 47%.
- PDU 3%.
- SAI 6%.
- Iluminación 2%.
- Conmutadores 1%.
Los principales esfuerzos de reducción de consumos son la refrigeración y TI.
## Distribución
- SAI, sistemas de alimentación ininterrumpida, centrado en el filtrado de la señal eléctrica y asegurado del suministro eléctrico.
- Módulos de potencia, convierten el circuito SAI a circuitos de menor amperaje, usable por los racks.
- Unidades de distribución eléctrica, rack para el despliegue de los módulos de potencia en las filas del cpd.
- Disyuntor, protector térmico del cable para evitar cortes por sobrecalentamiento del cable del módulo de potencia.
- PDU, regleta para la distribución de potencia y monitoreo de la misma a los equipos.
# Sistema de refrigeración
## Elementos de refrigeración
- Refrigeración por gas, compresor de aire (aire acondicionado).
- Refrigeración líquida, uso de un ciclo de refrigeración de agua e intercambio térmico interior.
## Arquitecturas de refrigeración
- Refrigeración por sala, enfriamiento completo de la sala (poco eficiente).
- Refrigeración por filas, enfriamiento por pasillo frío y caliente.
	- Los racks toman aire de un pasillo por donde entra el aire frío y expulsan el caliente a otra fila donde el sistema de refrigeración absorbe el aire caliente.
	- HACS, aislamiento del aire caliente para evitar la contaminación del aire frío.
- Enfriamiento por rack, enfriamiento de los racks individuales.
# Protección contra incendios
Sistemas de alarma y mitigación/extinción:
- Extintores
- Agua nebulizada, sistema que aumentan la humedad y reducen la temperatura para mitigar.
- Gas, gases que eliminan el oxígeno en el aire (no usados normalmente).
# Sistemas de control
Sensores de control de acceso para restringir la entrada al cpd y circuito cerrado de televisión por motivos 