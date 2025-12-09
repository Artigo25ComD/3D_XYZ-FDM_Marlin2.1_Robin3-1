| Critério                         | ATmega2560 (AVR, 8 bits)                 | STM32F407VGT6 (ARM Cortex-M4F, 32 bits)         |
|----------------------------------|------------------------------------------|--------------------------------------------------|
| Arquitetura                      | Harvard, 8 bits, sem FPU                 | ARMv7E-M, 32 bits, FPU (single precision)        |
| Clock                            | 16 MHz                                   | 168 MHz                                          |
| Flash                            | 256 KB                                   | 1 MB                                             |
| SRAM                             | 8 KB                                     | 192 KB                                           |
| Tensão lógica                    | 5 V                                      | 3,3 V                                            |
| UART / I2C / SPI                 | 4 / 1 / 1                                | até 6 / 3 / 3                                    |
| USB nativa                       | Não (conversor externo)                  | Sim (USB FS OTG)                                 |
| Timers / PWM                     | 6 timers (8/16 bits)                     | >10 timers (16/32 bits, avançados)               |
| ADC                              | 10 bits, até 16 canais                   | 12 bits, até 24 canais                           |
| Interface para SD                | SPI                                      | SDIO ou SPI                                      |
| Frequência de passos (Marlin)    | ≈10–15 kHz (típico)                      | ≈100–200 kHz (típico)                            |
| Recursos avançados no firmware   | Limitados por CPU/RAM                    | Linear Advance, Input Shaping, GUIs              |
| Drivers TMC (UART/SPI)           | Suporte via firmware                     | Suporte via firmware                             |


*Descrições rápidas por linha

    Arquitetura: define largura de dados e presença de FPU; 32 bits com FPU acelera cálculos de movimento/temperatura.
    Clock: frequência máxima do MCU; maior clock aumenta headroom para planejar passos e periféricos.
    Flash: armazena firmware e recursos; mais Flash permite features sem cortar módulos.
    SRAM: memória de runtime (buffers, pilha); mais SRAM permite buffers maiores de G-code e filtros.
    Tensão lógica: nível de I/O; atenção à compatibilidade 5 V ↔ 3,3 V em endstops e periféricos.
    UART/I2C/SPI: quantidade de interfaces seriais para drivers TMC, telas, sensores e módulos.
    USB nativa: elimina conversor externo e permite CDC/DFU/MSC, melhorando comunicação e atualização.
    Timers/PWM: mais e melhores timers dão pulsos mais estáveis para STEP e controle fino de fans/heaters.
    ADC: resolução/canais para ler termistores e sensores com mais precisão e velocidade.
    Interface para SD: SDIO é mais rápido e reduz gargalos ao ler G-code do cartão.
    Frequência de passos: taxa típica de geração de STEP; determina velocidades/ acelerações possíveis com microstepping alto.
    Recursos avançados no firmware: margem para habilitar recursos sem quedas de desempenho.
    Drivers TMC: ambos operam UART/SPI (configuração e diagnósticos) — dependem do firmware e da placa.

*Observações

    Valores “típicos”: variam com placa, compilação, features habilitadas e carga de I/O.
    Microstepping e rampas dependem dos drivers e da mecânica; o MCU só gera STEP/DIR e faz o planejamento.

    headroom: capacidade extra ou margem de segurança que o sistema possui além de seus requisitos operacionais nominais. 
