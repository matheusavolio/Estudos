

 #style   #text   #back
\033[    0;    33;     44m
sempre utilizar o \033(formato ANSI)
pode selecionar o style, text e/ou back que quiser, ou pode selecionar nenhum, utilizando o 0. Sempre separar com ";" o style, text, back que desejar

#style	         		                          #text                                              #back        
0 = none                                      30 = branco                                            40 = branco
1 = negrito                                   31 = vermelho                                        41 = vermelho
4 = underline                               32 = verde                                              42 = verde
7 = inverter config                       33 = amarelo                                          43 = amarelo
                              34 = azul                                                44 = azul
                              35 = rosa                                                45 = rosa
                              36 = ciano                                              46 = ciano
                              37 = cinza                                               47 = cinza

por exemplo:
`print("\033[4;30;45m Hello World!")
será impresso no terminal a mensagem "Hello World!" em um texto sublinhado e com o fundo rosa.

para a cor se limitar apenas a frase escolhida, damos um reset na cor ao final do texto escolhido para ter cor
`reset = "\033[0m"
`red = "\033[31m"
`green = "\033[32m"
`yellow = "\033[33m"
`blue = "\033[34m"
`pink = "\033[35m"
`cian = "\033[36m"
`grey = "\033[37m"``