# Processamentos Clássicos: Filtragem de sinais de áudio.
### Autor: Fábio Goródscy
### Para disciplina: CMU5380 - Processamento de Sinais Musicais: Técnicas e Percepção

## Sobre
Uma página web onde é possível observar espetro filtrado e não filtrado de uma fonte de som. Os filtros útilizados são passa alta e passa baixa, e podem ser utilizados em conjunto. As fontes de som podem ser via microfone ou por um arquivo de áudio. A frequência limitante dos filtros pode estar em um valor entre 10 e 22050. Também é possível definir um Q da qualidade do filtro, com valores entre 0.001 e 20.

## Experimento
Podemos considerar dois casos:
* Som do microfone: A princípio a página irá tentar obter o som do microfone. Se conseguir, o som será captado e direcionado para produção de 2 espectros, um deles com a combinação de filtros utilizado e outro apenas com o espectro original. 
* Som de arquivo de áudio: Também é possível carregar um arquivo de áudio, o arquivo será não apenas demonstrado nos espectros porém também será reproduzido nas caixas de som. A reprodução do arquivo será após a filtragem, então podemos observer as alterações que os filtros produzem diretamente.

Link para o experimento: (goo.gl/nZqWW6)
## Como Usar
Existem 3 botões, 2 slider, 1 campo numérico e 2 espectros. Descrevendo cada um:
* Botão branco: Esse botão seguirá o fluxo para carregar um arquivo. Ao clicar nele pela primeira vez, uma janela será aberta para escolha de um arquivo de áudio. Após escolher o arquivo o botão ficará desativado até o momento em que o arquivo termina de ser carregado. Quando o arquivo foi carregado, o botão consegue ser utilizado para reproduzir o arquivo ou para parar a execução.
* Botão Verde/Vermelho: Esse botão desativa/ativa os filtros. Verde significa que o respectivo filtro está ativados, vermelho significa que está desativado.
* Sliders: Os sliders permitem alterar a frequência limitante dos filtros. No caso do passa baixa, se a frequência estiver em 100hz, tudo que for superior a isso sofrerá filtragem. Já no passa alta, tudo que estivesse abaixo de 100hz seria filtrado.
* Q: O Q é um campo número, quanto mais alto mais restrito ficará o limiar do filtro.
* Espectro Filtrado: Resultado da filtragem demonstrado como espectro.
* Espectro Original: Espectro da fonte de som original.
