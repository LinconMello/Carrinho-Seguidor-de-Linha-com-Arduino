# Carrinho-Seguidor-de-Linha-com-Arduino

Objetivo do Projeto
O objetivo deste projeto é desenvolver um carrinho seguidor de linha preta, que também emite um alarme em situações específicas, como bifurcações e comandos recebidos via Bluetooth. O projeto foi desenvolvido em linguagem C, utilizando a plataforma Arduino, e visa demonstrar os princípios de controle de robôs autônomos e a integração de sensores para tomada de decisão.

Peças Utilizadas para o Desenvolvimento
Kit Chassi Robô 2WD: Base do carrinho, composta por duas rodas motorizadas.
Arduino Uno R3 + Cabo USB: Microcontrolador utilizado para programação e controle dos componentes.
Driver Motor Ponte H - L298N: Controlador dos motores, permitindo a inversão de rotação.
Sensor de Linha IR TCRT5000 - LM393: Sensores infravermelhos utilizados para detectar a linha preta.
Mini Protoboard 170 Pontos: Placa de prototipagem para conexões temporárias dos componentes.
Kit Jumpers Macho - Fêmea 10 unidades 20 cm: Cabos para conexões entre a protoboard e os componentes.
Kit Jumpers Macho - Macho 10 unidades 20 cm: Cabos para conexões diretas entre pinos.
Módulo Bluetooth RS232 HC-05: Módulo para comunicação sem fio com o carrinho.

Lógica do Código e Funcionamento
Configuração Inicial (setup)
No bloco setup, os pinos dos sensores, motores e buzzer são configurados como entradas ou saídas. A comunicação serial é inicializada para permitir a interação via Bluetooth.
Loop Principal (loop)
No loop principal, o código verifica continuamente se há dados disponíveis na comunicação serial (Bluetooth). Quando um comando é recebido, a função executarComandoBluetooth é chamada para processá-lo.
Os sensores de linha são lidos e, com base no seu estado, o carrinho decide a direção a seguir:
Ambos os sensores ativados: O carrinho se move para frente.
Apenas sensor esquerdo ativado: O carrinho vira à direita.
Apenas sensor direito ativado: O carrinho vira à esquerda.
Nenhum sensor ativado: O carrinho se move para trás.

Função de Execução de Comandos Bluetooth (executarComandoBluetooth)
Esta função processa comandos específicos recebidos via Bluetooth, como:
'A': Emite um som e para o carrinho por 3 segundos.
'B': Gira o carrinho 180 graus.
'D': Faz uma bifurcação para a direita.
'E': Faz uma bifurcação para a esquerda.

Função de Parada por Tempo (pararPorTempo)
Esta função para todos os motores do carrinho por um tempo especificado em milissegundos.

Agradecimentos
Gostaríamos de expressar nossos agradecimentos ao Professor Luís Pagotto por seu apoio e orientação ao longo deste projeto. Suas instruções foram fundamentais para o desenvolvimento do carrinho seguidor de linha. Este é o primeiro projeto de muitos, é apenas o início da jornada...
