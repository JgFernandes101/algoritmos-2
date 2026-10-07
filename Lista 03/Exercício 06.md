tipos
    Vetor = vetor[1..15] de string
função MenorNome (nome: Vetor; tam: inteiro): string
var
    aux: string
início
    se tam < 1 então
        retorne ""
    fim se
    se tam = 1 então
        retorne nome[1]
    fim se
    aux <- MenorNome(nome, tam - 1)
    se nome[tam] < aux então
        retorne nome[tam]
    senão
        retorne aux
    fim se
fim função
    
    
    
