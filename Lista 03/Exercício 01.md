função Maiusc2Minusc (s: string): string
var
    função M(aux: inteiro): string
    início
        se aux = 0 então
            retorne ""
        fim se
        se s[aux] >= 'A' e 'Z' >= s[aux] então
            retorne M(aux - 1) + chr(asc(s[aux]) + 32)
        senão
            retorne M(aux-1) + s[aux]
        fim se
    fim função
início
    retorne M(tamanho(s))
fim função