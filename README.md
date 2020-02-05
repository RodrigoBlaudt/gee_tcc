# Google Earth Engine - Extração de reflectância TOA e série temporal da Turbidez (NTU)

<!-- Link simples na mesma janela -->


Scripts utilizados em parte da metodologia para elaboração do trabalho de conclusão de curso: "Análise espaço temporal da turbidez do sistema de reservatórios em cascata do Rio Tietê via imagens orbitais: estudo de caso". 
Bacharelado em Geografia 2020 - Universidade Estadual de Maringá.

________________________________________________________________________________________________________________________________________

# Extração da reflectância TOA - TM/Landsat-5

Para elaboração da modelagem empírica foram coletados os valores de reflectância TOA (topo da atmosfera) em uma região de interesse (geometria: 3x3 pixels), concomitante as estações da CETESB. 

O script extrai os valores de reflectância TOA e os exporta (.csv) para o Google Drive do usuário. 

A seleção de dados sem cobertura de nuvens foi feita no LibreOffice com base nos valores da <i>'band assessment quality'</i> (BQA). Conforme a <a href="https://www.usgs.gov/land-resources/nli/landsat/landsat-collection-1-level-1-quality-assessment-band?qt-science_support_page_related_con=0#qt-science_support_page_related_con"> USGS</a>, os pixels não contaminados por nuvens apresentam BQA com valores de: 672, 676, 680 e 684.

Para este estudo não foi aplicado máscara de nuvens devido a utilização da reflectância TOA, e ausência, no Landsat 5, da banda de identificação de nuvens do tipo <i>cirrus</i>. 

O algoritmo de máscara de nuvens é funcional para reflectância em superfície, e tem ainda um melhor desempenho quando os satelites apresentam bandas para identificação destas nuvens - próximo a 1.365 μm, como o Landsat8/OLI (banda 9) ou Sentinel-2/MSI (banda 10).

https://code.earthengine.google.com/c700a17983e16e001f91b13d58e86c51

________________________________________________________________________________________________________________________________________
                                                            
# Baixo Tietê

                                                            
Script para estimativa da Turbidez via modelagem empírica, utilizando TM/Landsat 5 em reflectância no topo da atmosfera (TOA) 
em série histórica de 1984 a 2012.

Modelo empírico regionalizado sem distinção de estação - chuvosa ou seca, para o reservatório de Barra Bonita:

- R = 0,84; 
- R²ajustado = 0,83; 
- RMSE(NTU) = 4,09; 
- nRMSE(%) = 43,13 e 
- p-value = < 0,000001



| Coeficiente   | Valor         | p-value      |
| ------------- | ------------- |------------- |
| Intercepto    |   50,071      | 0,000637     |
|b3             | 1013,890      | 0,000001     |
|b1             | -493,525      | 0,000015     |
|b3/b2+b1       | -140,384      | 0,004430     |
|b4             | -182,019      | 0,016740     |


https://code.earthengine.google.com/1839d03bcf90ae87b20d3dada60df38a


________________________________________________________________________________________________________________________________________
         
# Médio e alto Tietê
                                                            
Script para estimativa da Turbidez via modelagem empírica, utilizando TM/Landsat 5 em reflectância no topo da atmosfera (TOA) 
em série histórica de 1984 a 2012.

Modelo empírico regionalizado sem distinção de estação - chuvosa ou seca, para os reservatórios do médio/alto rio Titê:
I) Bariri; II) Ibitinga; III) Promissão; IV) Nova Avanhandava; e V) Três Irmãos.

- R = 0,83; 
- R²ajustado = 0,82;
- RMSE(NTU) = 1,77;
- nRMSE(%) = 39,55 e 
- p-value = < 0,000001


| Coeficiente   | Valor         | p-value      |
| ------------- | ------------- |------------- |
| Intercepto    |   50,531      | 0,000001     |
|b3             | 1030,032      | 0,000001     |
|b1             | -525,184      | 0,000001     |
|b3/b2+b1       | -163,438      | 0,000001     |

 https://code.earthengine.google.com/678cc7f402eb2295762d9ba4cba99e35


________________________________________________________________________________________________________________________________________

# Aplicação da estimativa em imagens

Com o objetivo de visualizar os resultados dos modelos, foi elaborado um script para aplicação da turbidez estimada em imagens indíviduais. Neste script o modelo foi aplicado para a área do reservatório de Barra Bonita e Três Irmãos. 

Com pequenas alterações é possível aplicar a estimativa para qualquer imagem ou coleção, além de qualquer reservatório abordado.

https://code.earthengine.google.com/d32cd7a8295c36a51d33e5152f703a13


________________________________________________________________________________________________________________________________________
_
