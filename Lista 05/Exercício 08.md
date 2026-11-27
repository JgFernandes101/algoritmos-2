função trocar(nome: string; p: inteiro): lógico
var
    s1, s2: sequencia de real
    num, aux: real
    trocou: lógico
início
    se não abre(s1, nome) então
        retorne FALSO
    fim se
    se não abre(s2, nome) então
        fecha(s1)
        retorne FALSO
    fim se
    trocou <- FALSO
    enquanto não fds(s1) e p > 0 faça
        se p = 1 então
            leia(s2, num)
            aux <- num
            se não fds(s2) então
                leia(s2, num)
                escreva(s1, num)
                escreva(s1, aux)
                trocou <- VERDADEIRO
            fim se
        senão
            leia(s1, num)
            leia(s2, num)
        fim se
        p <- p - 1
    fim enquanto
    fecha(s1)
    fecha(s2)
    retorne trocou
fim função    
