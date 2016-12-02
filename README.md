# Integração de Processos: Processamento Paralelo e Serial.
### Autor: Fábio Goródscy
### Para disciplina: CMU5380 - Processamento de Sinais Musicais: Técnicas e Percepção

## Resumo
Neste experimento, demonstramos diferenças entre processamentos clássicos em sinais músicais, como filtros Passa Alta e Passa Baixa, no caso de utilização de uma combinação de filtros em forma serial ou em forma paralela. Para realizar o experimento foi desenvolvida uma página web utilizando Web Audio API onde um sinal de entrada será processado por um filtro Passa Baixa e um filtro Passa Alta, podendo ser selecionado se os filtros serão aplicados de forma serial ou paralela. Também é possível alterar a frequência de corte dos filtros para executar o experimento conforme será visto abaixo.

## Experimento
No experimento usamos Ruído Branco como áudio de entrada para melhor visualização e definimos 4 casos de combinações de filtros:
* Serial, Passa Baixa em 2 kHz, Passa Alta em 20 kHz: 
![Serial, Passa Baixa em 2 kHz, Passa Alta em 20 kHz](serial-pb2kpa20k.jpg)
O Passa Baixa será aplicado removendo quase todas as frequência e mantendo apenas o que está abaixo de 2 kHz. Por ser serial, o Passa Alta será aplicado após isso e removera frequências baixas como as que o Passa Baixa havia mantido. Como não há frequências altas no resultado do Passa Baixa, o resultado desse processamento em cadeia será um espectro vazio, ou um filtro Passa Nada.
* Serial. Passa Baixa em 20 kHz, Passa Alta em 2 kHz:
![Serial, Passa Baixa em 20 kHz, Passa Alta em 2 kHz](serial-pb20kpa2k.jpg)
Um filtro é aplicado após o outro, o Passa Baixa irá remover frequência abaixo de 2 kHz e o Passa Alta removerá o que está acima de 20 kHz, ficamos então com tudo que está entre 2 kHz e 20 kHz, portanto, obtemos um Passa Faixa.
* Paralelo, Passa Baixa em 2 kHz, Passa Alta em 20 kHz: 
![Paralelo, Passa Baixa em 2 kHz, Passa Alta em 20 kHz](paralelo-pb2kpa20k.jpg)
O filtro Passa baixa manterá apenas frequências abaixo de 2 kHz, mas como o processamento aqui é paralelo, as frequências que ele manteve são incluídas em conjunto com as frequências que o filtro Passa Alta irá deixar, que são frequências acima de 20 kHz. Então teremos um filtro Rejeita Banda, que reduzirá frequências entre o intervalo de 2 kHz e 20 kHz.
* Paralelo. Passa Baixa em 20 kHz, Passa Alta em 2 kHz:
![Paralelo, Passa Baixa em 20 kHz, Passa Alta em 2 kHz](paralelo-pb20kpa2k.jpg)
O filtro Passa Baixa irá manter a maioria das frequências, tudo que está abaixo de 20 kHz, e o Passa Alta irá manter tudo que está abaixo de 2 kHz. O resultado será um espectro onde todas as frequências estão presentes, pois algum dos dois filtros passavam alguma delas, portanto será um filtro Passa Tudo.

## Sistema
Para o processamento serial o sinal de entrada será processado primeiro pelo filtro Passa Baixa, e o resultado será enviado para o filtro Passa Alta, como no seguinte esquema: ![serial](serial.jpg)
Para o processamento paralelo o sinal de entrada será processado simultaneamente pelo filtro Passa Baixa e filtro Passa Alta, como no seguinte esquema![paralelo](paralelo.jpg)
O sistema permite alternar a qualquer momentro entre uma forma de processamento e a outra. O sinal de entrada pode ser um Ruído Branco, um arquivo de áudio de seu próprio computador ou a entrada do microfone de seu computador. O resultado filtrado do Ruído Branco e do Arquivo de Áudio será tocado pelo computador quando essas formas de entrada forem escolhidas. Em qualquer uma das formas de entradas, teremos o espectro do sinal original sendo visualizado e o espectro do sinal resultante. A frequência de corte dos filtros podem ser alteradas utilizando sliders.

Link para o experimento: (goo.gl/nZqWW6)
Link para o código: (github.com/fabiogoro/webfilters)

## Resultados
Podemos observar que o resultado final será totalmente dependente da forma de processamento dos sinais de entrada, e que podemos definir novos filtros de acordo com cada variação de combinação de processamentos. Isso é importante ser notado, pois caso não seja tomado em consideração poderá causar problemas para obter resultados desejados nos sinais que estão sendo processados.
