função MDC (a, b: inteiro): inteiro
var
    aux: inteiro
início
    se a <= 0 ou b <= 0 então
        retorne 0
    fim se
    se a = b então
        retorne a
    fim se
    se a < b então
        aux <- a
        a <- b
        b <- aux
    fim se
    se a mod b = 0 então
        retorne b
    fim se
    retorne MDC(b, a mod b)
fim função
