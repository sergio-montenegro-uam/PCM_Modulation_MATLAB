Sistema de Transmisión de Voz Usando Modulación PCM con Medición de Performance en Presencia de Ruido Gaussiano

El presente proyecto tiene como objetivo el desarrollo de un sistema de transmisión de voz utilizando modulación por codificación de pulsos (PCM), con medición de performance en presencia de ruido gaussiano.
La implementación del sistema se realizó en la interfaz de diseño de aplicaciones de MATLAB, lo que permitie una interacción más intuitiva y organizada con el procesamiento de señales. En cuanto a requerimientos
físicos, únicamente se empleo un computador, aunque se evalúa la posibilidad de utilizar un micrófono que optimice la captura del audio de voz, mejorando así la calidad del análisis y la fidelidad de los resultados 
obtenidos.
El sistema se compone de varias etapas fundamentales, iniciando con la adquisición de la señal de voz. Esta se puede obtener a partir de un archivo de audio pregrabado en formato WAV o mediante una grabación en 
tiempo real, lo que permite una mayor flexibilidad en la experimentación. Para garantizar la correcta digitalización de la señal, se empleará un muestreo a 8000 Hz, en concordancia con el Teorema de Muestreo de 
Nyquist, asegurando que no haya pérdida de información relevante dentro del espectro de la voz humana.
La señal capturada será sometida a un filtrado pasabajos con un ancho de banda de 4 kHz o, alternativamente, a un filtrado pasabandas en el rango de 20 Hz a 3800 Hz, lo cual es necesario para eliminar componentes
indeseadas y optimizar el contenido espectral de la señal. Esta etapa es crucial, dado que la mayor parte de la energía de la voz humana se encuentra en dicho intervalo de frecuencias. Para evaluar el comportamiento 
espectral de la señal antes y después de los procesos de filtrado y digitalización, se empleará la Transformada Rápida de Fourier (FFT), que permitirá una visualización detallada de los componentes de frecuencia.
Una vez la señal se encuentra adecuadamente filtrada, se procederá a la digitalización mediante los procesos de muestreo, cuantización y codificación. En la etapa de cuantización, para esta se utiliza la 
cuantización uniforme la cual es un proceso en el que el rango completo de amplitudes de una señal analógica se divide en intervalos iguales, asignando a cada intervalo un valor digital específico. 
Su principal ventaja radica en su simplicidad de implementación, ya que utiliza niveles de cuantización igualmente espaciados,. Para la codificación se asignará un código binario a cada nivel cuantizado, con una
cantidad de bits definida según el nivel de precisión deseado.
La señal codificada en PCM será luego transmitida a través de un canal simulado con ruido gaussiano blanco aditivo (AWGN), el cual se caracteriza por su distribución normal y su espectro plano. Se evaluará el 
impacto del ruido en la calidad de la señal mediante la simulación en diferentes condiciones de relación señal a ruido (SNR), utilizando valores de 0, 5, 10, 15, 20 y 30 dB. Para ello, se implementarán funciones 
específicas en MATLAB que permitirán la adición controlada del ruido gaussiano al canal de transmisión.
Al llegar al receptor, la señal estará afectada por el ruido, por lo que será necesario aplicar técnicas de detección y decodificación para su recuperación. Se establecerá un umbral de decisión para cada bit 
recibido, permitiendo interpretar correctamente los valores binarios transmitidos. Posteriormente, la señal será decodificada y decuantizada, utilizando el escalado correspondiente en la cuantización uniforme, 
con el fin de reconstruir la señal analógica original. Se comparará la señal recuperada con la señal original tanto en el dominio del tiempo como en el de la frecuencia, utilizando herramientas de análisis 
espectral y técnicas subjetivas de percepción auditiva para evaluar la calidad de la transmisión.
Para evaluar el desempeño del sistema, se implementarán métricas cuantitativas que permitan medir el impacto del ruido en la transmisión de voz digital. Entre estas métricas se incluyen:

 Relación señal a ruido (SNR):} Se calculará antes y después del canal de transmisión para cuantificar la degradación de la señal.
Error de cuantización (QE:} Es la diferencia entre el valor real de una señal analógica y su valor cuantizado al convertirla a formato digital. Este error ocurre porque, durante la cuantización, los valores 
continuos se redondean al nivel más cercano de una escala discreta predefinida
Medidas de calidad de la señal de voz:} Se evaluarán indicadores como el Signal-to-Distortion Ratio (SDR) y, si es posible, se utilizará el método PESQ (Perceptual Evaluation of Speech Quality) para obtener
una métrica subjetiva de la calidad del audio recuperado.
Diagrama de ojo:  Es una representación gráfica utilizada en comunicaciones digitales para evaluar la calidad de una señal recibida. Se obtiene superponiendo múltiples períodos de una señal digital, y su
forma resultante se asemeja a un ojo. Este diagrama permite visualizar errores por distorsión, ruido o sincronización, este será visualizado posterior a la codificacón y antes de agregar el ruido blanco gaussiano.
Adicionalmente, se realizarán simulaciones bajo distintas condiciones de ruido, observando el efecto de variaciones en la relación señal a ruido y cómo estas afectan la inteligibilidad y calidad del habla
transmitida. Se analizarán distintas configuraciones de cuantización y se comparará su impacto en la preservación de la información de la señal de voz. La evaluación de calidad se complementará con gráficos
espectrales, medición de errores y análisis perceptual.
En síntesis, este proyecto aborda el proceso completo de digitalización, transmisión y recuperación de voz mediante modulación PCM, integrando la simulación de ruido gaussiano para evaluar la robustez del 
sistema en condiciones adversas. La implementación en la interfaz de diseño de aplicaciones de MATLAB permitirá una gestión eficiente del sistema y una mejor visualización de los resultados. A través de 
la comparación entre diferentes esquemas de cuantización y la evaluación de métricas de calidad, se analizará cómo la presencia de ruido afecta la transmisión de voz y qué técnicas permiten minimizar su impacto.
La simulación en diferentes escenarios permitirá validar el desempeño del sistema y optimizar su configuración para mejorar la calidad en la recepción de voz digitalizada
