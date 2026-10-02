função reverso (n: inteiro): inteiro
var
    negativo, n_inverso: inteiro
    função R(n: inteiro; ref n_inverso: inteiro): inteiro
    início
        se n div 10 = 0 então
            retorne (n_inverso * 10 + n) * negativo
        fim se
        n_inverso <- n_inverso * 10 + n mod 10
        retorne R(n div 10, n_inverso)
    fim função
início
    se n < 0 então
        negativo <- -1
        n <- abs(n)
    senão
        negativo <- 1
    fim se
    n_inverso <- 0
    retorne R(n, n_inverso)
fim função
