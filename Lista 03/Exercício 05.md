
função QuantasVezesbEmA (a, b: inteiro): inteiro
var
    aux: inteiro
início
    se a < 0 ou b < 0 ou b > 9 então
        retorne -1
    fim se
    aux <- a mod 10
    a <- a div 10
    se a = 0 então
        se aux = b então
            retorne 1
        senão
            retorne 0
        fim se
    fim se
    se aux = b então
        retorne QuantasVezesbEmA(a, b) + 1
    senão
        retorne QuantasVezesbEmA(a, b)
    fim se
fim função
