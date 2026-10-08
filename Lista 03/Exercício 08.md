função Dec2Octal (n: inteiro): inteiro
var
    negativo: inteiro
    função oct (n: inteiro): inteiro
    início
        se n < 8 então
            retorne n
        fim se
        retorne oct(n div 8) * 10 + n mod 8
    fim função
início
    se n < 0 então
        n <- abs(n)
        negativo <- -1
    senão
        negativo <- 1
    fim se
    retorne oct(n) * negativo
fim função
