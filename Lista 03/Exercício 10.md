função Dec2Bin (s: string): inteiro
var
    bin, i: inteiro
    função String2Int (s: string): inteiro
    var
        aux: inteiro
    início
        aux <- 0
        para i de 1 até tamanho(s) faça
            aux <- aux * 10 + (asc(s[i]) - asc('0'))
        fim para
        retorne aux
    fim função
    função binario (n: inteiro): inteiro
    início
        se n < 2 então
            retorne n
        fim se
        retorne binario(n div 2) * 10 + n mod 2
    fim função
início
    se tamanho(s) = 0 então
        retorne -999999
    fim se
    bin <- String2Int(s)
    retorne binario(bin)
fim função
