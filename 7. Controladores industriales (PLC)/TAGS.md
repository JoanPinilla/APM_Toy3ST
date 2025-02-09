# Diccionario de TAGS
### Máquinas de inyección [INY]
1. Cuerpo Helicóptero [BHL]
2. Hélice Principal [HXP]
3. Hélice Secundaria [HXS]
4. Llantas [WHE]
5. Chasis Inferior Carro [CIC]
6. Chasis Superior Carro [CSC]
7. Carcasa Carro [CAC]
8. Chasis Inferior Tanque [CIT]
9. Chasis Superior Tanque [CST]
10. Torreta Tanque [TUT]
### Máquina de corte [CUT]
### Estaciones de desbarbado [DEB]
_DEB+PIEZA_
1. Cuerpo Helicóptero [DEB_BHL]
2. Hélice Principal [DEB_HXP]
3. Hélice Secundaria [DEB_HXS]
4. Llantas [DEB_WHE]
5. Chasis Inferior Carro [DEB_CIC]
6. Chasis Superior Carro [DEB_CSC]
7. Carcasa Carro [DEB_CAC]
8. Chasis Inferior Tanque [DEB_CIT]
9. Chasis Superior Tanque [DEB_CST]
10. Torreta Tanque [DEB_TUT]
### Empacadora [PAK]
1. Carro [CAR]
2. Tanque [TAN]
3. Helicóptero [HEL]
### Assembly [ABY]
1. Ruedas + Eje [TRA]
2. Chasis Inferior Carro + Chasis Superior Carro + TRA [TCR]
3. Chasis Inferior Tanque + Chasis Superior Tanque + TRA [TTN]
4. Hélice principal + Hélice Secundaria + Cuerpo helicóptero [AHL]
### Sensores [SEN]
Se nombran como _SEN_TIPO_MÁQUINA-ANTERIOR_N_, donde _N_ puede ser 1 para entrada, 2 para salida.
1. ÓPTICO [OPT]
    *	SEN_OPT_INY_WHE_1 / 2
    *	SEN_OPT_CUT_1 / 2
    *	SEN_OPT_INY_CIC_1 / 2
    *	SEN_OPT_INY_CSC_1 / 2
    *	SEN_OPT_INY_CAC_1 / 2
    *	SEN_OPT_INY_CIT_1 / 2
    *	SEN_OPT_INY_CST_1 / 2
    *	SEN_OPT_INY_TUT_1 / 2
    *	SEN_OPT_INY_BHL_1 / 2
    *	SEN_OPT_INY_HXP_1 / 2
    *	SEN_OPT_INY_HXS_1 / 2
    *	SEN_OPT_ABY_TCR_1 / 2
    *	SEN_OPT_ABY_TTN_1 / 2
    *	SEN_OPT_TO_ROB_A_1 / 2
    *	SEN_OPT_TO_ROB_B_1 / 2
    *	SEN_OPT_ROB_A_1 / 2
    *	SEN_OPT_ROB_B_1 / 2
### Robot [ROB]
1. Robot A [ROB_A]
2. Robot B [ROB_B]
### Bandas [BAN]
Se nombran como _BAN_ORIGEN_DESTINO_
1. BAN_INY_WHE_ABY_TRA
2. BAN_CUT_ABY_TRA
3. BAN_INY_CIC_DEB_CIC
4. BAN_INY_CSC_DEB_CSC
5. BAN_INY_CAC_DEB_CAC
6. BAN_INY_CIT_DEB_CIT
7. BAN_INY_CST_DEB_CST
8. BAN_INY_TUT_DEB_TUT
9. BAN_INY_BHL_DEB_BHL
10. BAN_INY_HXP_DEB_HXP
11. BAN_INY_HXS_DEB_HXS
12. BAN_ABY_TCR_ROB_A
13. BAN_ABY_TTN_ROB_B
14. BAN_TO_ROB_A
15. BAN_TO_ROB_B
16. BAN_ROB_A_PAK_CAR
17. BAN_ROB_B_PAK_TAN
18. BAN_ABY_AHL_PAK_HEL
