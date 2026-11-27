função somaPosição(nome: string; x: real): inteiro
var
    s1: sequência de real
    pos, soma: inteiro
    num: real
início
    se não abre(s1, nome) então
        retorne -99999
    fim se
    pos <- 0
    soma <- 0
    enquanto não fds(s1) faça
        pos <- pos + 1
        leia(s1, num)
        se num = x então
            soma <- soma + pos
        fim se
    fim enquanto
    fecha(s1)
    retorne soma
fim função
