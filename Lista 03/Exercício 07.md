função somatório(n: inteiro): inteiro
var
    soma_anterior, atual: inteiro
início
    se n < 0 então
        retorne -99999
    fim se
    se n = 0 então
        escreva(0)
        retorne 0
    fim se
    soma_anterior <- somatório(n-1)
    atual <- n + soma_anterior
    escreva(atual)
    retorne atual
fim função
