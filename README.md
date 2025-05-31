Varredura Wi-Fi com a Raspberry Pi Pico W
Este projeto demonstra como realizar uma varredura de redes Wi-Fi disponíveis utilizando a placa Raspberry Pi Pico W, exibindo informações como SSID, intensidade do sinal, canal, endereço MAC e modo de autenticação. Além disso, um LED conectado ao pino GPIO 13 pisca para indicar que a varredura está ativa.

🚀 Funcionalidades
✅ Inicialização do módulo Wi-Fi (CYW43439) integrado à Pico W.
✅ Callback para exibir resultados de varredura de redes Wi-Fi.
✅ LED vermelho no GPIO 13 pisca durante a varredura.
✅ A varredura é repetida a cada 10 segundos.

📝 Descrição do Código
Bibliotecas Importadas:

pico/stdlib.h e hardware/gpio.h para GPIO e funções básicas.

hardware/vreg.h e hardware/clocks.h para controle de regulador de tensão e clock.

pico/cyw43_arch.h para controle do Wi-Fi integrado.

Constantes:

led_pin_red = 13 → pino onde o LED vermelho está conectado.

Função scan_result():
Callback chamada automaticamente para cada rede Wi-Fi encontrada.
Mostra: SSID, RSSI, canal, endereço MAC e modo de autenticação.

Loop Principal (main()):
1️⃣ Inicializa o Wi-Fi.
2️⃣ Ativa o modo Station (STA).
3️⃣ Periodicamente inicia varreduras Wi-Fi.
4️⃣ Durante a varredura, o LED pisca a cada 200ms.
5️⃣ Após cada varredura, espera 10 segundos antes da próxima.

💡 Como Usar
1️⃣ Instale o SDK do Raspberry Pi Pico (Pico SDK).
2️⃣ Compile o código usando CMake ou seu ambiente de desenvolvimento preferido.
3️⃣ Conecte o LED ao pino GPIO 13 (com resistor de 220-330Ω em série).
4️⃣ Carregue o programa na Raspberry Pi Pico W.
5️⃣ Abra o terminal serial para ver os resultados das varreduras Wi-Fi.

📂 Estrutura de Arquivos
bash
Copiar
Editar
📁 Projeto
 ├── CMakeLists.txt  # Arquivo de configuração do CMake
 ├── main.c          # Código-fonte principal (este código)
 └── README.md       # Este arquivo de documentação
🔧 Requisitos
Raspberry Pi Pico W

SDK do Raspberry Pi Pico configurado

Ferramentas de compilação CMake e make

Terminal serial (ex.: minicom, putty, screen)

⚠️ Notas
Certifique-se de ter permissões para acessar a porta serial.

A Raspberry Pi Pico W precisa de firmware atualizado para funcionar com Wi-Fi.
