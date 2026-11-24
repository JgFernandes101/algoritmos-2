função mediaSeq(nome:string): real
var
    s: sequencia de inteiro
    num, soma, qnt: inteiro
início
    soma <- 0
    qnt <- 0
    se abre(s, nome) então
        enquanto não fds(s) faça
            leia(s, num)
            soma <- soma + num
            qnt <- qnt + 1
        fim enquanto
        fecha(s)
        se qnt = 0 então
            retorne -99999
        fim se
        retorne soma/qnt
    fim se
    retorne -999999
fim função
