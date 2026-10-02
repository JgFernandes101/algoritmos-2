c(0) = 1
c(1) = 1
c(n) = 1 + c(n-1)+ c(n-2); para todo n pertencente aos naturais e n >= 2

função FibonacciChamadas (n: inteiro): inteiro
var
    função FC(i: inteiro): inteiro
    início
        se i = 0 ou i = 1 então
            retorne 1
        fim se
        retorne 1 + FC(i-1) + FC(i-2)
    fim função
início
    se n < 0 então
        retorne -9999
    fim se
    retorne FC(n)
fim função
