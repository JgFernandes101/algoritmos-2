função Dec2Hexadec (n: inteiro): string
var
    negativo: string
    função hexadec (n: inteiro): string
    início
        se n < 10 então
            retorne "" + chr(asc('0') + n)
        fim se
        se n > 9 e n < 16 então
            retorne "" + chr(asc('A') + n - 10)
        fim se
        retorne hexadec(n div 16) + hexadec(n mod 16)
     fim função    
início
    se n < 0 então
        n <- abs(n)
        negativo <- "-"
    senão
        negativo <- ""
    fim se
    retorne negativo + hexadec(n)
fim função
    
