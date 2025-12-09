//Linha 71: Escolha do modelo da placa controladora 
#ifndef MOTHERBOARD
  #define MOTHERBOARD BOARD_MKS_ROBIN_NANO_V3_1
#endif


//Linha 84: Definição da porta serial
#define SERIAL_PORT -1

//Da linha 155 até a 176: Definição do modelo de driver utilizado para cada motor. 
//Definir como TMC2208 já que o TMC2225 não está disponivel na lista de drivers do marlin por ser basicamente um TMC2208 com melhorias térmicas. 
//Deixar comentadas as linhas de definição de drivers para motores não utilizados.
#define X_DRIVER_TYPE  TMC2208
#define Y_DRIVER_TYPE  TMC2208
#define Z_DRIVER_TYPE  TMC2208
// #define X2_DRIVER_TYPE A4988
// #define Y2_DRIVER_TYPE A4988
// #define Z2_DRIVER_TYPE A4988
// #define Z3_DRIVER_TYPE A4988
// #define Z4_DRIVER_TYPE A4988
// #define I_DRIVER_TYPE  A4988
// #define J_DRIVER_TYPE  A4988
// #define K_DRIVER_TYPE  A4988
// #define U_DRIVER_TYPE  A4988
// #define V_DRIVER_TYPE  A4988
// #define W_DRIVER_TYPE  A4988
#define E0_DRIVER_TYPE TMC2208
// #define E1_DRIVER_TYPE A4988
// #define E2_DRIVER_TYPE A4988
// #define E3_DRIVER_TYPE A4988
// #define E4_DRIVER_TYPE A4988
// #define E5_DRIVER_TYPE A4988
// #define E6_DRIVER_TYPE A4988
// #define E7_DRIVER_TYPE A4988

//Da linha 1270  até 1288: Configuração da identificação de acionamento dos endstops através do sinal  HIGH*/
#define X_MIN_ENDSTOP_HIT_STATE HIGH
#define X_MAX_ENDSTOP_HIT_STATE HIGH
#define Y_MIN_ENDSTOP_HIT_STATE HIGH
#define Y_MAX_ENDSTOP_HIT_STATE HIGH
#define Z_MIN_ENDSTOP_HIT_STATE HIGH
#define Z_MAX_ENDSTOP_HIT_STATE HIGH
#define I_MIN_ENDSTOP_HIT_STATE HIGH
#define I_MAX_ENDSTOP_HIT_STATE HIGH
#define J_MIN_ENDSTOP_HIT_STATE HIGH
#define J_MAX_ENDSTOP_HIT_STATE HIGH
#define K_MIN_ENDSTOP_HIT_STATE HIGH
#define K_MAX_ENDSTOP_HIT_STATE HIGH
#define U_MIN_ENDSTOP_HIT_STATE HIGH
#define U_MAX_ENDSTOP_HIT_STATE HIGH
#define V_MIN_ENDSTOP_HIT_STATE HIGH
#define V_MAX_ENDSTOP_HIT_STATE HIGH
#define W_MIN_ENDSTOP_HIT_STATE HIGH
#define W_MAX_ENDSTOP_HIT_STATE HIGH
#define Z_MIN_PROBE_ENDSTOP_HIT_STATE HIGH


//Linha 1336: Definição do SPU (Steps Per Unit)
#define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 93 }

//Linha 1874 até 1894: Definição da inversão das coordenadas do eixo X e Y para que X+ seja para a direita e Y+ seja para a frente

#define INVERT_X_DIR true
#define INVERT_Y_DIR true
#define INVERT_Z_DIR false
//#define INVERT_I_DIR false
//#define INVERT_J_DIR false
//#define INVERT_K_DIR false
//#define INVERT_U_DIR false
//#define INVERT_V_DIR false
//#define INVERT_W_DIR false


// @section extruder


// For direct drive extruder v9 set to true, for geared extruder set to false.
#define INVERT_E0_DIR true

//Da linha 1918 até 1920: Definição da direção do ponto inicial (home) dos eixos X, Y e Z 1=max e -1=min, como queremos o ponto 0,0,0 fica assim:
#define X_HOME_DIR -1
#define Y_HOME_DIR -1
#define Z_HOME_DIR -1

//Da linha 1946 até 1955: Definição do tamanho da área de impressão, e coordenada de homing, necessário pois temos endstops físicos somente nos pontos 0 de cada eixo
#define X_BED_SIZE 220
#define Y_BED_SIZE 220


// Limites (linear=mm, rotacional=°) depois de ir para o ponto home, corresponde às posições de parada.
#define X_MIN_POS 0
#define Y_MIN_POS 0
#define Z_MIN_POS 0
#define X_MAX_POS X_BED_SIZE
#define Y_MAX_POS Y_BED_SIZE
#define Z_MAX_POS 250

// linha 3397: Definição do modelo do display
#define MKS_TS35_V2_0
// linha 3397: Definição do modelo do display
#define MKS_TS35_V2_0

// linha 3502: Definição do tipo de interface do display
#define TFT_LVGL_UI

// linha 3567: Habilita o touch screen do display
#define TOUCH_SCREEN

// linha 3662: Habilita a função que permite controle mais preciso dos fans controláveis, sem habilitar essa função, os fans funcionam com controle apenas de liga e desliga, sem controle de potência 
#define FAN_SOFT_PWM

