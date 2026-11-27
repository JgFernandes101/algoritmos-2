função duplica(nome: string): lógico
var
    s1, s2: sequencia de inteiro
    num: inteiro
    qnt: inteiro
início
    qnt <- 0
    se não abre(s1, nome) então
        retorne FALSO
    fim se
    se não abre(s2, nome) então
        fecha(s1)
        retorne FALSO
    fim se
    enquanto não fds(s2) faça
        leia(s2, num)
        qnt <- qnt + 1
    fim enquanto
    enquanto qnt > 0 faça
        leia(s1, num)
        escreva(s2, num)
        qnt <- qnt - 1
    fim enquanto
    fecha(s1)
    fecha(s2)
    retorne VERDADEIRO
fim função
