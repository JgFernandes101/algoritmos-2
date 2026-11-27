procedimento escrevaMetade(nome: string)
var
    s1, s2: sequencia de real
    num, metade: real
    tam: inteiro
início
    tam <- 0
    se abre(s1, nome) então
        se abre(s2, nome) então
            enquanto não fds(s2) faça
                leia(s2, num)
                tam <- tam + 1
            fim enquanto
            metade <- tam/2
            enquanto não fds(s1) faça
                leia(s1, num)
                tam <- tam - 1
                se tam < metade então
                    escreva(num)
                fim se
            fim enquanto
            fecha(s2)
        fim se
        fecha(s1)
    fim se
fim procedimento          
