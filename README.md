# Google Earth Engine - Extração de reflectância TOA e série temporal da Turbidez (NTU)


Scripts utilizados em parte da metodologia para elaboração do trabalho de conclusão de curso: "Análise espaço temporal da turbidez do sistema de reservatórios em cascata do Rio Tietê via imagens orbitais: estudo de caso". 
Bacharelado em Geografia 2020 - Universidade Estadual de Maringá.



________________________________________________________________________________________________________________________________________
                                                            
# Script: Baixo Tietê

                                                            
Script para estimativa da Turbidez via modelagem empírica, utilizando TM/Landsat 5 em reflectância no topo da atmosfera (TOA) 
em série histórica de 1984 a 2012.

Modelo empírico regionalizado sem distinção de estação - chuvosa ou seca, para o reservatório de Barra Bonita:

R = 0,84 
R²ajustado = 0,83 
RMSE(NTU) = 4,09 
nRMSE(%) = 43,13 
p-value = < 0,000001


| Coeficiente   | Valor         | p-value      |
| ------------- | ------------- |------------- |
| Intercepto    | 50,071        | 0,000637     |
|b3             | 1013,890      | 0,000001     |
|b1             | -493,525      | 0,000015     |
|b3/b2+b1       | -140,384      | 0,004430     |
|b4             | -182,019      | 0,016740     |


 https://code.earthengine.google.com/1839d03bcf90ae87b20d3dada60df38a

________________________________________________________________________________________________________________________________________
         
# Script: Médio e alto Tietê
                                                            
Script para estimativa da Turbidez via modelagem empírica, utilizando TM/Landsat 5 em reflectância no topo da atmosfera (TOA) 
em série histórica de 1984 a 2012.

Modelo empírico regionalizado sem distinção de estação - chuvosa ou seca, para os reservatórios do médio/alto rio Titê:
I) Bariri; II) Ibitinga; III) Promissão; IV) Nova Avanhandava; e V) Três Irmãos.

R = 0,83 
R²ajustado = 0,82 
RMSE(NTU) = 1,77 
nRMSE(%) = 39,55 
p-value = < 0,000001


| Coeficiente   | Valor         | p-value      |
| ------------- | ------------- |------------- |
| Intercepto    | 50,531        | 0,000001     |
|b3             | 1030,032      | 0,000001     |
|b1             | -525,184      | 0,000001     |
|b3/b2+b1       | -163,438      | 0,000001     |


https://code.earthengine.google.com/019e58514726979ddc74efcfde402767
_
