# SD-PrioridadeThreadsJava

O código cria duas threads: uma de alta prioridade e outra de baixa prioridade. A thread de alta prioridade tenta ser executada mais vezes, mas como ela tem um comando sleep(10), ela faz pausas de 10 milissegundos, permitindo que a thread de baixa prioridade também tenha chances de rodar. A thread de baixa prioridade, por outro lado, continua rodando sem parar e imprimindo sua mensagem.

Mesmo que a thread de alta prioridade tenha mais chances de ser executada, isso não é garantido, pois o sistema operacional decide como distribuir o tempo de execução entre as threads. Ou seja, a thread de baixa prioridade pode, em alguns momentos, ser executada antes, principalmente quando a thread de alta prioridade está pausada no sleep.

Quando o método interrupt() é chamado, ele tenta interromper as threads, mas não garante que elas vão parar imediatamente. No caso da thread de baixa prioridade, como ela está em um laço infinito e não verifica interrupções, ela só vai parar quando o laço for interrompido de alguma forma. Já a thread de alta prioridade pode ser interrompida enquanto está no sleep, fazendo com que ela pare mais rapidamente.

Em resumo, o código mostra como controlar a prioridade das threads, mas a execução delas depende de como o sistema operacional decide gerenciar o tempo. Além disso, métodos como yield() e interrupt() ajudam a controlar a execução, mas a interrupção nem sempre vai funcionar como esperado.
