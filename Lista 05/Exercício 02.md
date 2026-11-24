função substituirSeq(nome, a, b: string): inteiro
var
    s1, s2: sequencia de string
    s: string
    qnt: inteiro
início
    qnt <- 0
    se não abre(s1, nome) então
        retorne -1
    fim se
    se não abre(s2, nome) então
        fecha(s1)
        retorne -1
    fim se
    enquanto não fds(s1) faça
        leia(s1, s)
        se s = a então
            escreva(s2, b)
            qnt <- qnt + 1
        senão
            leia(s2, s)
        fim se
    fim enquanto
    fecha(s1)
    fecha(s2)
    retorne qnt
fim função             
