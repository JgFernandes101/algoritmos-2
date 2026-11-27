função inserirOrdenado(nome: string; x: inteiro): lógico
var
    s1, s2: sequencia de inteiro
    num: inteiro
    inseriu: lógico
início
    inseriu <- FALSO
    se não abre(s1, nome) então
        retorne FALSO
    fim se
    se não abre(s2, nome) então
        fecha(s1)
        retorne FALSO
    fim se
    enquanto não fds(s2) faça
        leia(s1, num)
        se num > x e não inseriu então
            escreva(s2, x)
            x <- num
            enquanto não fds(s1) faça
                leia(s1, num)
                escreva(s2, x)
                x <- num
            fim enquanto
            escreva(s2, x)
            inseriu <- VERDADEIRO
        senão
            leia(s2, num)
        fim se
    fim enquanto
    se não inseriu então
        escreva(s1, x)
        inseriu <- VERDADEIRO
    fim se
    fecha(s1)
    fecha(s2)
    retorne inseriu
fim função
