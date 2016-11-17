                              1 ;--------------------------------------------------------
                              2 ; File Created by SDCC : free open source ANSI-C Compiler
                              3 ; Version 2.9.0 #5416 (Mar 26 2014) (UNIX)
                              4 ; This file was generated Mon Jul  4 17:32:12 2016
                              5 ;--------------------------------------------------------
                              6 	.module radio
                              7 	.optsdcc -mmcs51 --model-small
                              8 	
                              9 ;--------------------------------------------------------
                             10 ; Public variables in this module
                             11 ;--------------------------------------------------------
                             12 	.globl _main
                             13 	.globl _radio_init
                             14 	.globl _getpacket
                             15 	.globl _sendllap
                             16 	.globl _sendpacket
                             17 	.globl _switchchange
                             18 	.globl _convert_rssi
                             19 	.globl _cons_puthex16
                             20 	.globl _cons_puthex8
                             21 	.globl _cons_putsln
                             22 	.globl _cons_puts
                             23 	.globl _cons_putc
                             24 	.globl _nibble_to_char
                             25 	.globl _delay
                             26 	.globl _MODE
                             27 	.globl _RE
                             28 	.globl _SLAVE
                             29 	.globl _FE
                             30 	.globl _ERR
                             31 	.globl _RX_BYTE
                             32 	.globl _TX_BYTE
                             33 	.globl _ACTIVE
                             34 	.globl _B_7
                             35 	.globl _B_6
                             36 	.globl _B_5
                             37 	.globl _B_4
                             38 	.globl _B_3
                             39 	.globl _B_2
                             40 	.globl _B_1
                             41 	.globl _B_0
                             42 	.globl _WDTIF
                             43 	.globl _P1IF
                             44 	.globl _UTX1IF
                             45 	.globl _UTX0IF
                             46 	.globl _P2IF
                             47 	.globl _ACC_7
                             48 	.globl _ACC_6
                             49 	.globl _ACC_5
                             50 	.globl _ACC_4
                             51 	.globl _ACC_3
                             52 	.globl _ACC_2
                             53 	.globl _ACC_1
                             54 	.globl _ACC_0
                             55 	.globl _OVFIM
                             56 	.globl _T4CH1IF
                             57 	.globl _T4CH0IF
                             58 	.globl _T4OVFIF
                             59 	.globl _T3CH1IF
                             60 	.globl _T3CH0IF
                             61 	.globl _T3OVFIF
                             62 	.globl _CY
                             63 	.globl _AC
                             64 	.globl _F0
                             65 	.globl _RS1
                             66 	.globl _RS0
                             67 	.globl _OV
                             68 	.globl _F1
                             69 	.globl _P
                             70 	.globl _STIF
                             71 	.globl _P0IF
                             72 	.globl _T4IF
                             73 	.globl _T3IF
                             74 	.globl _T2IF
                             75 	.globl _T1IF
                             76 	.globl _DMAIF
                             77 	.globl _P0IE
                             78 	.globl _T4IE
                             79 	.globl _T3IE
                             80 	.globl _T2IE
                             81 	.globl _T1IE
                             82 	.globl _DMAIE
                             83 	.globl _EA
                             84 	.globl _STIE
                             85 	.globl _ENCIE
                             86 	.globl _URX1IE
                             87 	.globl _URX0IE
                             88 	.globl _ADCIE
                             89 	.globl _RFTXRXIE
                             90 	.globl _P2_7
                             91 	.globl _P2_6
                             92 	.globl _P2_5
                             93 	.globl _P2_4
                             94 	.globl _P2_3
                             95 	.globl _P2_2
                             96 	.globl _P2_1
                             97 	.globl _P2_0
                             98 	.globl _ENCIF_1
                             99 	.globl _ENCIF_0
                            100 	.globl _P1_7
                            101 	.globl _P1_6
                            102 	.globl _P1_5
                            103 	.globl _P1_4
                            104 	.globl _P1_3
                            105 	.globl _P1_2
                            106 	.globl _P1_1
                            107 	.globl _P1_0
                            108 	.globl _URX1IF
                            109 	.globl _ADCIF
                            110 	.globl _URX0IF
                            111 	.globl _IT1
                            112 	.globl _RFTXRXIF
                            113 	.globl _IT0
                            114 	.globl _P0_7
                            115 	.globl _P0_6
                            116 	.globl _P0_5
                            117 	.globl _P0_4
                            118 	.globl _P0_3
                            119 	.globl _P0_2
                            120 	.globl _P0_1
                            121 	.globl _P0_0
                            122 	.globl _P2DIR
                            123 	.globl _P1DIR
                            124 	.globl _P0DIR
                            125 	.globl _U1GCR
                            126 	.globl _U1UCR
                            127 	.globl _U1BAUD
                            128 	.globl _U1DBUF
                            129 	.globl _U1CSR
                            130 	.globl _P2INP
                            131 	.globl _P1INP
                            132 	.globl _P2SEL
                            133 	.globl _P1SEL
                            134 	.globl _P0SEL
                            135 	.globl _ADCCFG
                            136 	.globl _PERCFG
                            137 	.globl _B
                            138 	.globl _T4CC1
                            139 	.globl _T4CCTL1
                            140 	.globl _T4CC0
                            141 	.globl _T4CCTL0
                            142 	.globl _T4CTL
                            143 	.globl _T4CNT
                            144 	.globl _RFIF
                            145 	.globl _IRCON2
                            146 	.globl _T1CCTL2
                            147 	.globl _T1CCTL1
                            148 	.globl _T1CCTL0
                            149 	.globl _T1CTL
                            150 	.globl _T1CNTH
                            151 	.globl _T1CNTL
                            152 	.globl _RFST
                            153 	.globl _ACC
                            154 	.globl _T1CC2H
                            155 	.globl _T1CC2L
                            156 	.globl _T1CC1H
                            157 	.globl _T1CC1L
                            158 	.globl _T1CC0H
                            159 	.globl _T1CC0L
                            160 	.globl _RFD
                            161 	.globl _TIMIF
                            162 	.globl _DMAREQ
                            163 	.globl _DMAARM
                            164 	.globl _DMA0CFGH
                            165 	.globl _DMA0CFGL
                            166 	.globl _DMA1CFGH
                            167 	.globl _DMA1CFGL
                            168 	.globl _DMAIRQ
                            169 	.globl _PSW
                            170 	.globl _T3CC1
                            171 	.globl _T3CCTL1
                            172 	.globl _T3CC0
                            173 	.globl _T3CCTL0
                            174 	.globl _T3CTL
                            175 	.globl _T3CNT
                            176 	.globl _WDCTL
                            177 	.globl __SFRC8
                            178 	.globl _MEMCTR
                            179 	.globl _CLKCON
                            180 	.globl _U0GCR
                            181 	.globl _U0UCR
                            182 	.globl __SFRC3
                            183 	.globl _U0BAUD
                            184 	.globl _U0DBUF
                            185 	.globl _IRCON
                            186 	.globl __SFRBF
                            187 	.globl _SLEEP
                            188 	.globl _RNDH
                            189 	.globl _RNDL
                            190 	.globl _ADCH
                            191 	.globl _ADCL
                            192 	.globl _IP1
                            193 	.globl _IEN1
                            194 	.globl __SFRB7
                            195 	.globl _ADCCON3
                            196 	.globl _ADCCON2
                            197 	.globl _ADCCON1
                            198 	.globl _ENCCS
                            199 	.globl _ENCDO
                            200 	.globl _ENCDI
                            201 	.globl __SFRB0
                            202 	.globl _FWDATA
                            203 	.globl _FCTL
                            204 	.globl _FADDRH
                            205 	.globl _FADDRL
                            206 	.globl _FWT
                            207 	.globl __SFRAA
                            208 	.globl _IP0
                            209 	.globl _IEN0
                            210 	.globl __SFRA7
                            211 	.globl _WORTIME1
                            212 	.globl _WORTIME0
                            213 	.globl _WOREVT1
                            214 	.globl _WOREVT0
                            215 	.globl _WORCTRL
                            216 	.globl _WORIRQ
                            217 	.globl _P2
                            218 	.globl __SFR9F
                            219 	.globl _T2CTL
                            220 	.globl _T2PR
                            221 	.globl _T2CT
                            222 	.globl _S1CON
                            223 	.globl _IEN2
                            224 	.globl __SFR99
                            225 	.globl _S0CON
                            226 	.globl __SFR97
                            227 	.globl __SFR96
                            228 	.globl __SFR95
                            229 	.globl __SFR94
                            230 	.globl __XPAGE
                            231 	.globl _MPAGE
                            232 	.globl _DPS
                            233 	.globl _RFIM
                            234 	.globl _P1
                            235 	.globl _P0INP
                            236 	.globl __SFR8E
                            237 	.globl _P1IEN
                            238 	.globl _PICTL
                            239 	.globl _P2IFG
                            240 	.globl _P1IFG
                            241 	.globl _P0IFG
                            242 	.globl _TCON
                            243 	.globl _PCON
                            244 	.globl _U0CSR
                            245 	.globl _DPH1
                            246 	.globl _DPL1
                            247 	.globl _DPH0
                            248 	.globl _DPL0
                            249 	.globl _SP
                            250 	.globl _P0
                            251 	.globl _X_P2DIR
                            252 	.globl _X_P1DIR
                            253 	.globl _X_P0DIR
                            254 	.globl _X_U1GCR
                            255 	.globl _X_U1UCR
                            256 	.globl _X_U1BAUD
                            257 	.globl _X_U1DBUF
                            258 	.globl _X_U1CSR
                            259 	.globl _X_P2INP
                            260 	.globl _X_P1INP
                            261 	.globl _X_P2SEL
                            262 	.globl _X_P1SEL
                            263 	.globl _X_P0SEL
                            264 	.globl _X_ADCCFG
                            265 	.globl _X_PERCFG
                            266 	.globl __NA_B
                            267 	.globl _X_T4CC1
                            268 	.globl _X_T4CCTL1
                            269 	.globl _X_T4CC0
                            270 	.globl _X_T4CCTL0
                            271 	.globl _X_T4CTL
                            272 	.globl _X_T4CNT
                            273 	.globl _X_RFIF
                            274 	.globl __NA_IRCON2
                            275 	.globl _X_T1CCTL2
                            276 	.globl _X_T1CCTL1
                            277 	.globl _X_T1CCTL0
                            278 	.globl _X_T1CTL
                            279 	.globl _X_T1CNTH
                            280 	.globl _X_T1CNTL
                            281 	.globl _X_RFST
                            282 	.globl __NA_ACC
                            283 	.globl _X_T1CC2H
                            284 	.globl _X_T1CC2L
                            285 	.globl _X_T1CC1H
                            286 	.globl _X_T1CC1L
                            287 	.globl _X_T1CC0H
                            288 	.globl _X_T1CC0L
                            289 	.globl _X_RFD
                            290 	.globl _X_TIMIF
                            291 	.globl _X_DMAREQ
                            292 	.globl _X_DMAARM
                            293 	.globl _X_DMA0CFGH
                            294 	.globl _X_DMA0CFGL
                            295 	.globl _X_DMA1CFGH
                            296 	.globl _X_DMA1CFGL
                            297 	.globl _X_DMAIRQ
                            298 	.globl __NA_PSW
                            299 	.globl _X_T3CC1
                            300 	.globl _X_T3CCTL1
                            301 	.globl _X_T3CC0
                            302 	.globl _X_T3CCTL0
                            303 	.globl _X_T3CTL
                            304 	.globl _X_T3CNT
                            305 	.globl _X_WDCTL
                            306 	.globl __X_SFRC8
                            307 	.globl _X_MEMCTR
                            308 	.globl _X_CLKCON
                            309 	.globl _X_U0GCR
                            310 	.globl _X_U0UCR
                            311 	.globl __X_SFRC3
                            312 	.globl _X_U0BAUD
                            313 	.globl _X_U0DBUF
                            314 	.globl __NA_IRCON
                            315 	.globl __X_SFRBF
                            316 	.globl _X_SLEEP
                            317 	.globl _X_RNDH
                            318 	.globl _X_RNDL
                            319 	.globl _X_ADCH
                            320 	.globl _X_ADCL
                            321 	.globl __NA_IP1
                            322 	.globl __NA_IEN1
                            323 	.globl __X_SFRB7
                            324 	.globl _X_ADCCON3
                            325 	.globl _X_ADCCON2
                            326 	.globl _X_ADCCON1
                            327 	.globl _X_ENCCS
                            328 	.globl _X_ENCDO
                            329 	.globl _X_ENCDI
                            330 	.globl __X_SFRB0
                            331 	.globl _X_FWDATA
                            332 	.globl _X_FCTL
                            333 	.globl _X_FADDRH
                            334 	.globl _X_FADDRL
                            335 	.globl _X_FWT
                            336 	.globl __X_SFRAA
                            337 	.globl __NA_IP0
                            338 	.globl __NA_IEN0
                            339 	.globl __X_SFRA7
                            340 	.globl _X_WORTIME1
                            341 	.globl _X_WORTIME0
                            342 	.globl _X_WOREVT1
                            343 	.globl _X_WOREVT0
                            344 	.globl _X_WORCTRL
                            345 	.globl _X_WORIRQ
                            346 	.globl __NA_P2
                            347 	.globl __X_SFR9F
                            348 	.globl _X_T2CTL
                            349 	.globl _X_T2PR
                            350 	.globl _X_T2CT
                            351 	.globl __NA_S1CON
                            352 	.globl __NA_IEN2
                            353 	.globl __X_SFR99
                            354 	.globl __NA_S0CON
                            355 	.globl __X_SFR97
                            356 	.globl __X_SFR96
                            357 	.globl __X_SFR95
                            358 	.globl __X_SFR94
                            359 	.globl _X_MPAGE
                            360 	.globl __NA_DPS
                            361 	.globl _X_RFIM
                            362 	.globl __NA_P1
                            363 	.globl _X_P0INP
                            364 	.globl __X_SFR8E
                            365 	.globl _X_P1IEN
                            366 	.globl _X_PICTL
                            367 	.globl _X_P2IFG
                            368 	.globl _X_P1IFG
                            369 	.globl _X_P0IFG
                            370 	.globl __NA_TCON
                            371 	.globl __NA_PCON
                            372 	.globl _X_U0CSR
                            373 	.globl __NA_DPH1
                            374 	.globl __NA_DPL1
                            375 	.globl __NA_DPH0
                            376 	.globl __NA_DPL0
                            377 	.globl __NA_SP
                            378 	.globl __NA_P0
                            379 	.globl _I2SCLKF2
                            380 	.globl _I2SCLKF1
                            381 	.globl _I2SCLKF0
                            382 	.globl _I2SSTAT
                            383 	.globl _I2SWCNT
                            384 	.globl _I2SDATH
                            385 	.globl _I2SDATL
                            386 	.globl _I2SCFG1
                            387 	.globl _I2SCFG0
                            388 	.globl _VCO_VC_DAC
                            389 	.globl _PKTSTATUS
                            390 	.globl _MARCSTATE
                            391 	.globl _RSSI
                            392 	.globl _LQI
                            393 	.globl _FREQEST
                            394 	.globl _VERSION
                            395 	.globl _PARTNUM
                            396 	.globl __XREGDF35
                            397 	.globl __XREGDF34
                            398 	.globl __XREGDF33
                            399 	.globl __XREGDF32
                            400 	.globl _IOCFG0
                            401 	.globl _IOCFG1
                            402 	.globl _IOCFG2
                            403 	.globl _PA_TABLE0
                            404 	.globl _PA_TABLE1
                            405 	.globl _PA_TABLE2
                            406 	.globl _PA_TABLE3
                            407 	.globl _PA_TABLE4
                            408 	.globl _PA_TABLE5
                            409 	.globl _PA_TABLE6
                            410 	.globl _PA_TABLE7
                            411 	.globl __XREGDF26
                            412 	.globl _TEST0
                            413 	.globl _TEST1
                            414 	.globl _TEST2
                            415 	.globl __XREGDF22
                            416 	.globl __XREGDF21
                            417 	.globl __XREGDF20
                            418 	.globl _FSCAL0
                            419 	.globl _FSCAL1
                            420 	.globl _FSCAL2
                            421 	.globl _FSCAL3
                            422 	.globl _FREND0
                            423 	.globl _FREND1
                            424 	.globl _AGCCTRL0
                            425 	.globl _AGCCTRL1
                            426 	.globl _AGCCTRL2
                            427 	.globl _BSCFG
                            428 	.globl _FOCCFG
                            429 	.globl _MCSM0
                            430 	.globl _MCSM1
                            431 	.globl _MCSM2
                            432 	.globl _DEVIATN
                            433 	.globl _MDMCFG0
                            434 	.globl _MDMCFG1
                            435 	.globl _MDMCFG2
                            436 	.globl _MDMCFG3
                            437 	.globl _MDMCFG4
                            438 	.globl _FREQ0
                            439 	.globl _FREQ1
                            440 	.globl _FREQ2
                            441 	.globl _FSCTRL0
                            442 	.globl _FSCTRL1
                            443 	.globl _CHANNR
                            444 	.globl _ADDR
                            445 	.globl _PKTCTRL0
                            446 	.globl _PKTCTRL1
                            447 	.globl _PKTLEN
                            448 	.globl _SYNC0
                            449 	.globl _SYNC1
                            450 	.globl _MDMCTRL0H
                            451 	.globl _sendllap_PARM_2
                            452 	.globl _rssi_offset
                            453 	.globl _preamble
                            454 	.globl _rftxrx_isr
                            455 ;--------------------------------------------------------
                            456 ; special function registers
                            457 ;--------------------------------------------------------
                            458 	.area RSEG    (DATA)
                    0080    459 _P0	=	0x0080
                    0081    460 _SP	=	0x0081
                    0082    461 _DPL0	=	0x0082
                    0083    462 _DPH0	=	0x0083
                    0084    463 _DPL1	=	0x0084
                    0085    464 _DPH1	=	0x0085
                    0086    465 _U0CSR	=	0x0086
                    0087    466 _PCON	=	0x0087
                    0088    467 _TCON	=	0x0088
                    0089    468 _P0IFG	=	0x0089
                    008A    469 _P1IFG	=	0x008a
                    008B    470 _P2IFG	=	0x008b
                    008C    471 _PICTL	=	0x008c
                    008D    472 _P1IEN	=	0x008d
                    008E    473 __SFR8E	=	0x008e
                    008F    474 _P0INP	=	0x008f
                    0090    475 _P1	=	0x0090
                    0091    476 _RFIM	=	0x0091
                    0092    477 _DPS	=	0x0092
                    0093    478 _MPAGE	=	0x0093
                    0093    479 __XPAGE	=	0x0093
                    0094    480 __SFR94	=	0x0094
                    0095    481 __SFR95	=	0x0095
                    0096    482 __SFR96	=	0x0096
                    0097    483 __SFR97	=	0x0097
                    0098    484 _S0CON	=	0x0098
                    0099    485 __SFR99	=	0x0099
                    009A    486 _IEN2	=	0x009a
                    009B    487 _S1CON	=	0x009b
                    009C    488 _T2CT	=	0x009c
                    009D    489 _T2PR	=	0x009d
                    009E    490 _T2CTL	=	0x009e
                    009F    491 __SFR9F	=	0x009f
                    00A0    492 _P2	=	0x00a0
                    00A1    493 _WORIRQ	=	0x00a1
                    00A2    494 _WORCTRL	=	0x00a2
                    00A3    495 _WOREVT0	=	0x00a3
                    00A4    496 _WOREVT1	=	0x00a4
                    00A5    497 _WORTIME0	=	0x00a5
                    00A6    498 _WORTIME1	=	0x00a6
                    00A7    499 __SFRA7	=	0x00a7
                    00A8    500 _IEN0	=	0x00a8
                    00A9    501 _IP0	=	0x00a9
                    00AA    502 __SFRAA	=	0x00aa
                    00AB    503 _FWT	=	0x00ab
                    00AC    504 _FADDRL	=	0x00ac
                    00AD    505 _FADDRH	=	0x00ad
                    00AE    506 _FCTL	=	0x00ae
                    00AF    507 _FWDATA	=	0x00af
                    00B0    508 __SFRB0	=	0x00b0
                    00B1    509 _ENCDI	=	0x00b1
                    00B2    510 _ENCDO	=	0x00b2
                    00B3    511 _ENCCS	=	0x00b3
                    00B4    512 _ADCCON1	=	0x00b4
                    00B5    513 _ADCCON2	=	0x00b5
                    00B6    514 _ADCCON3	=	0x00b6
                    00B7    515 __SFRB7	=	0x00b7
                    00B8    516 _IEN1	=	0x00b8
                    00B9    517 _IP1	=	0x00b9
                    00BA    518 _ADCL	=	0x00ba
                    00BB    519 _ADCH	=	0x00bb
                    00BC    520 _RNDL	=	0x00bc
                    00BD    521 _RNDH	=	0x00bd
                    00BE    522 _SLEEP	=	0x00be
                    00BF    523 __SFRBF	=	0x00bf
                    00C0    524 _IRCON	=	0x00c0
                    00C1    525 _U0DBUF	=	0x00c1
                    00C2    526 _U0BAUD	=	0x00c2
                    00C3    527 __SFRC3	=	0x00c3
                    00C4    528 _U0UCR	=	0x00c4
                    00C5    529 _U0GCR	=	0x00c5
                    00C6    530 _CLKCON	=	0x00c6
                    00C7    531 _MEMCTR	=	0x00c7
                    00C8    532 __SFRC8	=	0x00c8
                    00C9    533 _WDCTL	=	0x00c9
                    00CA    534 _T3CNT	=	0x00ca
                    00CB    535 _T3CTL	=	0x00cb
                    00CC    536 _T3CCTL0	=	0x00cc
                    00CD    537 _T3CC0	=	0x00cd
                    00CE    538 _T3CCTL1	=	0x00ce
                    00CF    539 _T3CC1	=	0x00cf
                    00D0    540 _PSW	=	0x00d0
                    00D1    541 _DMAIRQ	=	0x00d1
                    00D2    542 _DMA1CFGL	=	0x00d2
                    00D3    543 _DMA1CFGH	=	0x00d3
                    00D4    544 _DMA0CFGL	=	0x00d4
                    00D5    545 _DMA0CFGH	=	0x00d5
                    00D6    546 _DMAARM	=	0x00d6
                    00D7    547 _DMAREQ	=	0x00d7
                    00D8    548 _TIMIF	=	0x00d8
                    00D9    549 _RFD	=	0x00d9
                    00DA    550 _T1CC0L	=	0x00da
                    00DB    551 _T1CC0H	=	0x00db
                    00DC    552 _T1CC1L	=	0x00dc
                    00DD    553 _T1CC1H	=	0x00dd
                    00DE    554 _T1CC2L	=	0x00de
                    00DF    555 _T1CC2H	=	0x00df
                    00E0    556 _ACC	=	0x00e0
                    00E1    557 _RFST	=	0x00e1
                    00E2    558 _T1CNTL	=	0x00e2
                    00E3    559 _T1CNTH	=	0x00e3
                    00E4    560 _T1CTL	=	0x00e4
                    00E5    561 _T1CCTL0	=	0x00e5
                    00E6    562 _T1CCTL1	=	0x00e6
                    00E7    563 _T1CCTL2	=	0x00e7
                    00E8    564 _IRCON2	=	0x00e8
                    00E9    565 _RFIF	=	0x00e9
                    00EA    566 _T4CNT	=	0x00ea
                    00EB    567 _T4CTL	=	0x00eb
                    00EC    568 _T4CCTL0	=	0x00ec
                    00ED    569 _T4CC0	=	0x00ed
                    00EE    570 _T4CCTL1	=	0x00ee
                    00EF    571 _T4CC1	=	0x00ef
                    00F0    572 _B	=	0x00f0
                    00F1    573 _PERCFG	=	0x00f1
                    00F2    574 _ADCCFG	=	0x00f2
                    00F3    575 _P0SEL	=	0x00f3
                    00F4    576 _P1SEL	=	0x00f4
                    00F5    577 _P2SEL	=	0x00f5
                    00F6    578 _P1INP	=	0x00f6
                    00F7    579 _P2INP	=	0x00f7
                    00F8    580 _U1CSR	=	0x00f8
                    00F9    581 _U1DBUF	=	0x00f9
                    00FA    582 _U1BAUD	=	0x00fa
                    00FB    583 _U1UCR	=	0x00fb
                    00FC    584 _U1GCR	=	0x00fc
                    00FD    585 _P0DIR	=	0x00fd
                    00FE    586 _P1DIR	=	0x00fe
                    00FF    587 _P2DIR	=	0x00ff
                            588 ;--------------------------------------------------------
                            589 ; special function bits
                            590 ;--------------------------------------------------------
                            591 	.area RSEG    (DATA)
                    0080    592 _P0_0	=	0x0080
                    0081    593 _P0_1	=	0x0081
                    0082    594 _P0_2	=	0x0082
                    0083    595 _P0_3	=	0x0083
                    0084    596 _P0_4	=	0x0084
                    0085    597 _P0_5	=	0x0085
                    0086    598 _P0_6	=	0x0086
                    0087    599 _P0_7	=	0x0087
                    0088    600 _IT0	=	0x0088
                    0089    601 _RFTXRXIF	=	0x0089
                    008A    602 _IT1	=	0x008a
                    008B    603 _URX0IF	=	0x008b
                    008D    604 _ADCIF	=	0x008d
                    008F    605 _URX1IF	=	0x008f
                    0090    606 _P1_0	=	0x0090
                    0091    607 _P1_1	=	0x0091
                    0092    608 _P1_2	=	0x0092
                    0093    609 _P1_3	=	0x0093
                    0094    610 _P1_4	=	0x0094
                    0095    611 _P1_5	=	0x0095
                    0096    612 _P1_6	=	0x0096
                    0097    613 _P1_7	=	0x0097
                    0098    614 _ENCIF_0	=	0x0098
                    0099    615 _ENCIF_1	=	0x0099
                    00A0    616 _P2_0	=	0x00a0
                    00A1    617 _P2_1	=	0x00a1
                    00A2    618 _P2_2	=	0x00a2
                    00A3    619 _P2_3	=	0x00a3
                    00A4    620 _P2_4	=	0x00a4
                    00A5    621 _P2_5	=	0x00a5
                    00A6    622 _P2_6	=	0x00a6
                    00A7    623 _P2_7	=	0x00a7
                    00A8    624 _RFTXRXIE	=	0x00a8
                    00A9    625 _ADCIE	=	0x00a9
                    00AA    626 _URX0IE	=	0x00aa
                    00AB    627 _URX1IE	=	0x00ab
                    00AC    628 _ENCIE	=	0x00ac
                    00AD    629 _STIE	=	0x00ad
                    00AF    630 _EA	=	0x00af
                    00B8    631 _DMAIE	=	0x00b8
                    00B9    632 _T1IE	=	0x00b9
                    00BA    633 _T2IE	=	0x00ba
                    00BB    634 _T3IE	=	0x00bb
                    00BC    635 _T4IE	=	0x00bc
                    00BD    636 _P0IE	=	0x00bd
                    00C0    637 _DMAIF	=	0x00c0
                    00C1    638 _T1IF	=	0x00c1
                    00C2    639 _T2IF	=	0x00c2
                    00C3    640 _T3IF	=	0x00c3
                    00C4    641 _T4IF	=	0x00c4
                    00C5    642 _P0IF	=	0x00c5
                    00C7    643 _STIF	=	0x00c7
                    00D0    644 _P	=	0x00d0
                    00D1    645 _F1	=	0x00d1
                    00D2    646 _OV	=	0x00d2
                    00D3    647 _RS0	=	0x00d3
                    00D4    648 _RS1	=	0x00d4
                    00D5    649 _F0	=	0x00d5
                    00D6    650 _AC	=	0x00d6
                    00D7    651 _CY	=	0x00d7
                    00D8    652 _T3OVFIF	=	0x00d8
                    00D9    653 _T3CH0IF	=	0x00d9
                    00DA    654 _T3CH1IF	=	0x00da
                    00DB    655 _T4OVFIF	=	0x00db
                    00DC    656 _T4CH0IF	=	0x00dc
                    00DD    657 _T4CH1IF	=	0x00dd
                    00DE    658 _OVFIM	=	0x00de
                    00E0    659 _ACC_0	=	0x00e0
                    00E1    660 _ACC_1	=	0x00e1
                    00E2    661 _ACC_2	=	0x00e2
                    00E3    662 _ACC_3	=	0x00e3
                    00E4    663 _ACC_4	=	0x00e4
                    00E5    664 _ACC_5	=	0x00e5
                    00E6    665 _ACC_6	=	0x00e6
                    00E7    666 _ACC_7	=	0x00e7
                    00E8    667 _P2IF	=	0x00e8
                    00E9    668 _UTX0IF	=	0x00e9
                    00EA    669 _UTX1IF	=	0x00ea
                    00EB    670 _P1IF	=	0x00eb
                    00EC    671 _WDTIF	=	0x00ec
                    00F0    672 _B_0	=	0x00f0
                    00F1    673 _B_1	=	0x00f1
                    00F2    674 _B_2	=	0x00f2
                    00F3    675 _B_3	=	0x00f3
                    00F4    676 _B_4	=	0x00f4
                    00F5    677 _B_5	=	0x00f5
                    00F6    678 _B_6	=	0x00f6
                    00F7    679 _B_7	=	0x00f7
                    00F8    680 _ACTIVE	=	0x00f8
                    00F9    681 _TX_BYTE	=	0x00f9
                    00FA    682 _RX_BYTE	=	0x00fa
                    00FB    683 _ERR	=	0x00fb
                    00FC    684 _FE	=	0x00fc
                    00FD    685 _SLAVE	=	0x00fd
                    00FE    686 _RE	=	0x00fe
                    00FF    687 _MODE	=	0x00ff
                            688 ;--------------------------------------------------------
                            689 ; overlayable register banks
                            690 ;--------------------------------------------------------
                            691 	.area REG_BANK_0	(REL,OVR,DATA)
   0000                     692 	.ds 8
                            693 ;--------------------------------------------------------
                            694 ; internal ram data
                            695 ;--------------------------------------------------------
                            696 	.area DSEG    (DATA)
   0008                     697 _packet_index:
   0008                     698 	.ds 1
   0009                     699 _preamble::
   0009                     700 	.ds 3
   000C                     701 _rssi_offset::
   000C                     702 	.ds 2
   000E                     703 _sendllap_PARM_2:
   000E                     704 	.ds 2
   0010                     705 _getpacket_llapmsg_1_1:
   0010                     706 	.ds 13
   001D                     707 _main_swstate_1_1:
   001D                     708 	.ds 2
                            709 ;--------------------------------------------------------
                            710 ; overlayable items in internal ram 
                            711 ;--------------------------------------------------------
                            712 	.area	OSEG    (OVR,DATA)
                            713 	.area	OSEG    (OVR,DATA)
                            714 	.area	OSEG    (OVR,DATA)
                            715 ;--------------------------------------------------------
                            716 ; Stack segment in internal ram 
                            717 ;--------------------------------------------------------
                            718 	.area	SSEG	(DATA)
   002A                     719 __start__stack:
   002A                     720 	.ds	1
                            721 
                            722 ;--------------------------------------------------------
                            723 ; indirectly addressable internal ram data
                            724 ;--------------------------------------------------------
                            725 	.area ISEG    (DATA)
                            726 ;--------------------------------------------------------
                            727 ; absolute internal ram data
                            728 ;--------------------------------------------------------
                            729 	.area IABS    (ABS,DATA)
                            730 	.area IABS    (ABS,DATA)
                            731 ;--------------------------------------------------------
                            732 ; bit data
                            733 ;--------------------------------------------------------
                            734 	.area BSEG    (BIT)
                            735 ;--------------------------------------------------------
                            736 ; paged external ram data
                            737 ;--------------------------------------------------------
                            738 	.area PSEG    (PAG,XDATA)
                            739 ;--------------------------------------------------------
                            740 ; external ram data
                            741 ;--------------------------------------------------------
                            742 	.area XSEG    (XDATA)
                    DF02    743 _MDMCTRL0H	=	0xdf02
                    DF00    744 _SYNC1	=	0xdf00
                    DF01    745 _SYNC0	=	0xdf01
                    DF02    746 _PKTLEN	=	0xdf02
                    DF03    747 _PKTCTRL1	=	0xdf03
                    DF04    748 _PKTCTRL0	=	0xdf04
                    DF05    749 _ADDR	=	0xdf05
                    DF06    750 _CHANNR	=	0xdf06
                    DF07    751 _FSCTRL1	=	0xdf07
                    DF08    752 _FSCTRL0	=	0xdf08
                    DF09    753 _FREQ2	=	0xdf09
                    DF0A    754 _FREQ1	=	0xdf0a
                    DF0B    755 _FREQ0	=	0xdf0b
                    DF0C    756 _MDMCFG4	=	0xdf0c
                    DF0D    757 _MDMCFG3	=	0xdf0d
                    DF0E    758 _MDMCFG2	=	0xdf0e
                    DF0F    759 _MDMCFG1	=	0xdf0f
                    DF10    760 _MDMCFG0	=	0xdf10
                    DF11    761 _DEVIATN	=	0xdf11
                    DF12    762 _MCSM2	=	0xdf12
                    DF13    763 _MCSM1	=	0xdf13
                    DF14    764 _MCSM0	=	0xdf14
                    DF15    765 _FOCCFG	=	0xdf15
                    DF16    766 _BSCFG	=	0xdf16
                    DF17    767 _AGCCTRL2	=	0xdf17
                    DF18    768 _AGCCTRL1	=	0xdf18
                    DF19    769 _AGCCTRL0	=	0xdf19
                    DF1A    770 _FREND1	=	0xdf1a
                    DF1B    771 _FREND0	=	0xdf1b
                    DF1C    772 _FSCAL3	=	0xdf1c
                    DF1D    773 _FSCAL2	=	0xdf1d
                    DF1E    774 _FSCAL1	=	0xdf1e
                    DF1F    775 _FSCAL0	=	0xdf1f
                    DF20    776 __XREGDF20	=	0xdf20
                    DF21    777 __XREGDF21	=	0xdf21
                    DF22    778 __XREGDF22	=	0xdf22
                    DF23    779 _TEST2	=	0xdf23
                    DF24    780 _TEST1	=	0xdf24
                    DF25    781 _TEST0	=	0xdf25
                    DF26    782 __XREGDF26	=	0xdf26
                    DF27    783 _PA_TABLE7	=	0xdf27
                    DF28    784 _PA_TABLE6	=	0xdf28
                    DF29    785 _PA_TABLE5	=	0xdf29
                    DF2A    786 _PA_TABLE4	=	0xdf2a
                    DF2B    787 _PA_TABLE3	=	0xdf2b
                    DF2C    788 _PA_TABLE2	=	0xdf2c
                    DF2D    789 _PA_TABLE1	=	0xdf2d
                    DF2E    790 _PA_TABLE0	=	0xdf2e
                    DF2F    791 _IOCFG2	=	0xdf2f
                    DF30    792 _IOCFG1	=	0xdf30
                    DF31    793 _IOCFG0	=	0xdf31
                    DF32    794 __XREGDF32	=	0xdf32
                    DF33    795 __XREGDF33	=	0xdf33
                    DF34    796 __XREGDF34	=	0xdf34
                    DF35    797 __XREGDF35	=	0xdf35
                    DF36    798 _PARTNUM	=	0xdf36
                    DF37    799 _VERSION	=	0xdf37
                    DF38    800 _FREQEST	=	0xdf38
                    DF39    801 _LQI	=	0xdf39
                    DF3A    802 _RSSI	=	0xdf3a
                    DF3B    803 _MARCSTATE	=	0xdf3b
                    DF3C    804 _PKTSTATUS	=	0xdf3c
                    DF3D    805 _VCO_VC_DAC	=	0xdf3d
                    DF40    806 _I2SCFG0	=	0xdf40
                    DF41    807 _I2SCFG1	=	0xdf41
                    DF42    808 _I2SDATL	=	0xdf42
                    DF43    809 _I2SDATH	=	0xdf43
                    DF44    810 _I2SWCNT	=	0xdf44
                    DF45    811 _I2SSTAT	=	0xdf45
                    DF46    812 _I2SCLKF0	=	0xdf46
                    DF47    813 _I2SCLKF1	=	0xdf47
                    DF48    814 _I2SCLKF2	=	0xdf48
                    DF80    815 __NA_P0	=	0xdf80
                    DF81    816 __NA_SP	=	0xdf81
                    DF82    817 __NA_DPL0	=	0xdf82
                    DF83    818 __NA_DPH0	=	0xdf83
                    DF84    819 __NA_DPL1	=	0xdf84
                    DF85    820 __NA_DPH1	=	0xdf85
                    DF86    821 _X_U0CSR	=	0xdf86
                    DF87    822 __NA_PCON	=	0xdf87
                    DF88    823 __NA_TCON	=	0xdf88
                    DF89    824 _X_P0IFG	=	0xdf89
                    DF8A    825 _X_P1IFG	=	0xdf8a
                    DF8B    826 _X_P2IFG	=	0xdf8b
                    DF8C    827 _X_PICTL	=	0xdf8c
                    DF8D    828 _X_P1IEN	=	0xdf8d
                    DF8E    829 __X_SFR8E	=	0xdf8e
                    DF8F    830 _X_P0INP	=	0xdf8f
                    DF90    831 __NA_P1	=	0xdf90
                    DF91    832 _X_RFIM	=	0xdf91
                    DF92    833 __NA_DPS	=	0xdf92
                    DF93    834 _X_MPAGE	=	0xdf93
                    DF94    835 __X_SFR94	=	0xdf94
                    DF95    836 __X_SFR95	=	0xdf95
                    DF96    837 __X_SFR96	=	0xdf96
                    DF97    838 __X_SFR97	=	0xdf97
                    DF98    839 __NA_S0CON	=	0xdf98
                    DF99    840 __X_SFR99	=	0xdf99
                    DF9A    841 __NA_IEN2	=	0xdf9a
                    DF9B    842 __NA_S1CON	=	0xdf9b
                    DF9C    843 _X_T2CT	=	0xdf9c
                    DF9D    844 _X_T2PR	=	0xdf9d
                    DF9E    845 _X_T2CTL	=	0xdf9e
                    DF9F    846 __X_SFR9F	=	0xdf9f
                    DFA0    847 __NA_P2	=	0xdfa0
                    DFA1    848 _X_WORIRQ	=	0xdfa1
                    DFA2    849 _X_WORCTRL	=	0xdfa2
                    DFA3    850 _X_WOREVT0	=	0xdfa3
                    DFA4    851 _X_WOREVT1	=	0xdfa4
                    DFA5    852 _X_WORTIME0	=	0xdfa5
                    DFA6    853 _X_WORTIME1	=	0xdfa6
                    DFA7    854 __X_SFRA7	=	0xdfa7
                    DFA8    855 __NA_IEN0	=	0xdfa8
                    DFA9    856 __NA_IP0	=	0xdfa9
                    DFAA    857 __X_SFRAA	=	0xdfaa
                    DFAB    858 _X_FWT	=	0xdfab
                    DFAC    859 _X_FADDRL	=	0xdfac
                    DFAD    860 _X_FADDRH	=	0xdfad
                    DFAE    861 _X_FCTL	=	0xdfae
                    DFAF    862 _X_FWDATA	=	0xdfaf
                    DFB0    863 __X_SFRB0	=	0xdfb0
                    DFB1    864 _X_ENCDI	=	0xdfb1
                    DFB2    865 _X_ENCDO	=	0xdfb2
                    DFB3    866 _X_ENCCS	=	0xdfb3
                    DFB4    867 _X_ADCCON1	=	0xdfb4
                    DFB5    868 _X_ADCCON2	=	0xdfb5
                    DFB6    869 _X_ADCCON3	=	0xdfb6
                    DFB7    870 __X_SFRB7	=	0xdfb7
                    DFB8    871 __NA_IEN1	=	0xdfb8
                    DFB9    872 __NA_IP1	=	0xdfb9
                    DFBA    873 _X_ADCL	=	0xdfba
                    DFBB    874 _X_ADCH	=	0xdfbb
                    DFBC    875 _X_RNDL	=	0xdfbc
                    DFBD    876 _X_RNDH	=	0xdfbd
                    DFBE    877 _X_SLEEP	=	0xdfbe
                    DFBF    878 __X_SFRBF	=	0xdfbf
                    DFC0    879 __NA_IRCON	=	0xdfc0
                    DFC1    880 _X_U0DBUF	=	0xdfc1
                    DFC2    881 _X_U0BAUD	=	0xdfc2
                    DFC3    882 __X_SFRC3	=	0xdfc3
                    DFC4    883 _X_U0UCR	=	0xdfc4
                    DFC5    884 _X_U0GCR	=	0xdfc5
                    DFC6    885 _X_CLKCON	=	0xdfc6
                    DFC7    886 _X_MEMCTR	=	0xdfc7
                    DFC8    887 __X_SFRC8	=	0xdfc8
                    DFC9    888 _X_WDCTL	=	0xdfc9
                    DFCA    889 _X_T3CNT	=	0xdfca
                    DFCB    890 _X_T3CTL	=	0xdfcb
                    DFCC    891 _X_T3CCTL0	=	0xdfcc
                    DFCD    892 _X_T3CC0	=	0xdfcd
                    DFCE    893 _X_T3CCTL1	=	0xdfce
                    DFCF    894 _X_T3CC1	=	0xdfcf
                    DFD0    895 __NA_PSW	=	0xdfd0
                    DFD1    896 _X_DMAIRQ	=	0xdfd1
                    DFD2    897 _X_DMA1CFGL	=	0xdfd2
                    DFD3    898 _X_DMA1CFGH	=	0xdfd3
                    DFD4    899 _X_DMA0CFGL	=	0xdfd4
                    DFD5    900 _X_DMA0CFGH	=	0xdfd5
                    DFD6    901 _X_DMAARM	=	0xdfd6
                    DFD7    902 _X_DMAREQ	=	0xdfd7
                    DFD8    903 _X_TIMIF	=	0xdfd8
                    DFD9    904 _X_RFD	=	0xdfd9
                    DFDA    905 _X_T1CC0L	=	0xdfda
                    DFDB    906 _X_T1CC0H	=	0xdfdb
                    DFDC    907 _X_T1CC1L	=	0xdfdc
                    DFDD    908 _X_T1CC1H	=	0xdfdd
                    DFDE    909 _X_T1CC2L	=	0xdfde
                    DFDF    910 _X_T1CC2H	=	0xdfdf
                    DFE0    911 __NA_ACC	=	0xdfe0
                    DFE1    912 _X_RFST	=	0xdfe1
                    DFE2    913 _X_T1CNTL	=	0xdfe2
                    DFE3    914 _X_T1CNTH	=	0xdfe3
                    DFE4    915 _X_T1CTL	=	0xdfe4
                    DFE5    916 _X_T1CCTL0	=	0xdfe5
                    DFE6    917 _X_T1CCTL1	=	0xdfe6
                    DFE7    918 _X_T1CCTL2	=	0xdfe7
                    DFE8    919 __NA_IRCON2	=	0xdfe8
                    DFE9    920 _X_RFIF	=	0xdfe9
                    DFEA    921 _X_T4CNT	=	0xdfea
                    DFEB    922 _X_T4CTL	=	0xdfeb
                    DFEC    923 _X_T4CCTL0	=	0xdfec
                    DFED    924 _X_T4CC0	=	0xdfed
                    DFEE    925 _X_T4CCTL1	=	0xdfee
                    DFEF    926 _X_T4CC1	=	0xdfef
                    DFF0    927 __NA_B	=	0xdff0
                    DFF1    928 _X_PERCFG	=	0xdff1
                    DFF2    929 _X_ADCCFG	=	0xdff2
                    DFF3    930 _X_P0SEL	=	0xdff3
                    DFF4    931 _X_P1SEL	=	0xdff4
                    DFF5    932 _X_P2SEL	=	0xdff5
                    DFF6    933 _X_P1INP	=	0xdff6
                    DFF7    934 _X_P2INP	=	0xdff7
                    DFF8    935 _X_U1CSR	=	0xdff8
                    DFF9    936 _X_U1DBUF	=	0xdff9
                    DFFA    937 _X_U1BAUD	=	0xdffa
                    DFFB    938 _X_U1UCR	=	0xdffb
                    DFFC    939 _X_U1GCR	=	0xdffc
                    DFFD    940 _X_P0DIR	=	0xdffd
                    DFFE    941 _X_P1DIR	=	0xdffe
                    DFFF    942 _X_P2DIR	=	0xdfff
   F000                     943 _packet:
   F000                     944 	.ds 255
                            945 ;--------------------------------------------------------
                            946 ; absolute external ram data
                            947 ;--------------------------------------------------------
                            948 	.area XABS    (ABS,XDATA)
                            949 ;--------------------------------------------------------
                            950 ; external initialized ram data
                            951 ;--------------------------------------------------------
                            952 	.area XISEG   (XDATA)
                            953 	.area HOME    (CODE)
                            954 	.area GSINIT0 (CODE)
                            955 	.area GSINIT1 (CODE)
                            956 	.area GSINIT2 (CODE)
                            957 	.area GSINIT3 (CODE)
                            958 	.area GSINIT4 (CODE)
                            959 	.area GSINIT5 (CODE)
                            960 	.area GSINIT  (CODE)
                            961 	.area GSFINAL (CODE)
                            962 	.area CSEG    (CODE)
                            963 ;--------------------------------------------------------
                            964 ; interrupt vector 
                            965 ;--------------------------------------------------------
                            966 	.area HOME    (CODE)
   0000                     967 __interrupt_vect:
   0000 02 00 0B            968 	ljmp	__sdcc_gsinit_startup
   0003 02 01 FD            969 	ljmp	_rftxrx_isr
                            970 ;--------------------------------------------------------
                            971 ; global & static initialisations
                            972 ;--------------------------------------------------------
                            973 	.area HOME    (CODE)
                            974 	.area GSINIT  (CODE)
                            975 	.area GSFINAL (CODE)
                            976 	.area GSINIT  (CODE)
                            977 	.globl __sdcc_gsinit_startup
                            978 	.globl __sdcc_program_startup
                            979 	.globl __start__stack
                            980 	.globl __mcs51_genXINIT
                            981 	.globl __mcs51_genXRAMCLEAR
                            982 	.globl __mcs51_genRAMCLEAR
                            983 ;	radio.c:12: uint8_t preamble[] = {0x0E, 0x5A, 0xA5};
   0064 75 09 0E            984 	mov	_preamble,#0x0E
   0067 75 0A 5A            985 	mov	(_preamble + 0x0001),#0x5A
   006A 75 0B A5            986 	mov	(_preamble + 0x0002),#0xA5
                            987 	.area GSFINAL (CODE)
   006D 02 00 06            988 	ljmp	__sdcc_program_startup
                            989 ;--------------------------------------------------------
                            990 ; Home
                            991 ;--------------------------------------------------------
                            992 	.area HOME    (CODE)
                            993 	.area HOME    (CODE)
   0006                     994 __sdcc_program_startup:
   0006 12 06 2C            995 	lcall	_main
                            996 ;	return from main will lock up
   0009 80 FE               997 	sjmp .
                            998 ;--------------------------------------------------------
                            999 ; code
                           1000 ;--------------------------------------------------------
                           1001 	.area CSEG    (CODE)
                           1002 ;------------------------------------------------------------
                           1003 ;Allocation info for local variables in function 'delay'
                           1004 ;------------------------------------------------------------
                           1005 ;msec                      Allocated to registers r2 r3 
                           1006 ;i                         Allocated to registers r4 r5 
                           1007 ;j                         Allocated to registers r6 r7 
                           1008 ;------------------------------------------------------------
                           1009 ;	radio.c:15: void delay(int msec) {
                           1010 ;	-----------------------------------------
                           1011 ;	 function delay
                           1012 ;	-----------------------------------------
   0070                    1013 _delay:
                    0002   1014 	ar2 = 0x02
                    0003   1015 	ar3 = 0x03
                    0004   1016 	ar4 = 0x04
                    0005   1017 	ar5 = 0x05
                    0006   1018 	ar6 = 0x06
                    0007   1019 	ar7 = 0x07
                    0000   1020 	ar0 = 0x00
                    0001   1021 	ar1 = 0x01
   0070 AA 82              1022 	mov	r2,dpl
   0072 AB 83              1023 	mov	r3,dph
                           1024 ;	radio.c:18: for (i=0; i<msec; i++)
   0074 7C 00              1025 	mov	r4,#0x00
   0076 7D 00              1026 	mov	r5,#0x00
   0078                    1027 00104$:
   0078 C3                 1028 	clr	c
   0079 EC                 1029 	mov	a,r4
   007A 9A                 1030 	subb	a,r2
   007B ED                 1031 	mov	a,r5
   007C 64 80              1032 	xrl	a,#0x80
   007E 8B F0              1033 	mov	b,r3
   0080 63 F0 80           1034 	xrl	b,#0x80
   0083 95 F0              1035 	subb	a,b
   0085 50 14              1036 	jnc	00108$
                           1037 ;	radio.c:19: for (j=0; j<1000; j++);
   0087 7E E8              1038 	mov	r6,#0xE8
   0089 7F 03              1039 	mov	r7,#0x03
   008B                    1040 00103$:
   008B 1E                 1041 	dec	r6
   008C BE FF 01           1042 	cjne	r6,#0xff,00117$
   008F 1F                 1043 	dec	r7
   0090                    1044 00117$:
   0090 EE                 1045 	mov	a,r6
   0091 4F                 1046 	orl	a,r7
   0092 70 F7              1047 	jnz	00103$
                           1048 ;	radio.c:18: for (i=0; i<msec; i++)
   0094 0C                 1049 	inc	r4
   0095 BC 00 E0           1050 	cjne	r4,#0x00,00104$
   0098 0D                 1051 	inc	r5
   0099 80 DD              1052 	sjmp	00104$
   009B                    1053 00108$:
   009B 22                 1054 	ret
                           1055 ;------------------------------------------------------------
                           1056 ;Allocation info for local variables in function 'nibble_to_char'
                           1057 ;------------------------------------------------------------
                           1058 ;nibble                    Allocated to registers r2 
                           1059 ;------------------------------------------------------------
                           1060 ;	radio.c:22: char nibble_to_char(uint8_t nibble) {
                           1061 ;	-----------------------------------------
                           1062 ;	 function nibble_to_char
                           1063 ;	-----------------------------------------
   009C                    1064 _nibble_to_char:
   009C AA 82              1065 	mov	r2,dpl
                           1066 ;	radio.c:23: if (nibble < 0xA)
   009E BA 0A 00           1067 	cjne	r2,#0x0A,00106$
   00A1                    1068 00106$:
   00A1 50 06              1069 	jnc	00102$
                           1070 ;	radio.c:24: return nibble + '0';
   00A3 74 30              1071 	mov	a,#0x30
   00A5 2A                 1072 	add	a,r2
   00A6 F5 82              1073 	mov	dpl,a
   00A8 22                 1074 	ret
   00A9                    1075 00102$:
                           1076 ;	radio.c:25: return nibble - 0xA + 'A';
   00A9 74 37              1077 	mov	a,#0x37
   00AB 2A                 1078 	add	a,r2
   00AC F5 82              1079 	mov	dpl,a
   00AE 22                 1080 	ret
                           1081 ;------------------------------------------------------------
                           1082 ;Allocation info for local variables in function 'cons_putc'
                           1083 ;------------------------------------------------------------
                           1084 ;ch                        Allocated to registers 
                           1085 ;------------------------------------------------------------
                           1086 ;	radio.c:28: void cons_putc(uint8_t ch) {
                           1087 ;	-----------------------------------------
                           1088 ;	 function cons_putc
                           1089 ;	-----------------------------------------
   00AF                    1090 _cons_putc:
   00AF 85 82 C1           1091 	mov	_U0DBUF,dpl
                           1092 ;	radio.c:30: while(!(U0CSR & U0CSR_TX_BYTE)); // wait for byte to be transmitted                                                                     
   00B2                    1093 00101$:
   00B2 E5 86              1094 	mov	a,_U0CSR
   00B4 30 E1 FB           1095 	jnb	acc.1,00101$
                           1096 ;	radio.c:31: U0CSR &= ~U0CSR_TX_BYTE;         // Clear transmit byte status                                                                          
   00B7 53 86 FD           1097 	anl	_U0CSR,#0xFD
   00BA 22                 1098 	ret
                           1099 ;------------------------------------------------------------
                           1100 ;Allocation info for local variables in function 'cons_puts'
                           1101 ;------------------------------------------------------------
                           1102 ;s                         Allocated to registers r2 r3 r4 
                           1103 ;------------------------------------------------------------
                           1104 ;	radio.c:34: void cons_puts(const char *s)
                           1105 ;	-----------------------------------------
                           1106 ;	 function cons_puts
                           1107 ;	-----------------------------------------
   00BB                    1108 _cons_puts:
   00BB AA 82              1109 	mov	r2,dpl
   00BD AB 83              1110 	mov	r3,dph
   00BF AC F0              1111 	mov	r4,b
                           1112 ;	radio.c:36: while(0 != *s)
   00C1                    1113 00101$:
   00C1 8A 82              1114 	mov	dpl,r2
   00C3 8B 83              1115 	mov	dph,r3
   00C5 8C F0              1116 	mov	b,r4
   00C7 12 07 92           1117 	lcall	__gptrget
   00CA FD                 1118 	mov	r5,a
   00CB 60 18              1119 	jz	00104$
                           1120 ;	radio.c:37: cons_putc((uint8_t)(*s++));
   00CD 8D 82              1121 	mov	dpl,r5
   00CF 0A                 1122 	inc	r2
   00D0 BA 00 01           1123 	cjne	r2,#0x00,00110$
   00D3 0B                 1124 	inc	r3
   00D4                    1125 00110$:
   00D4 C0 02              1126 	push	ar2
   00D6 C0 03              1127 	push	ar3
   00D8 C0 04              1128 	push	ar4
   00DA 12 00 AF           1129 	lcall	_cons_putc
   00DD D0 04              1130 	pop	ar4
   00DF D0 03              1131 	pop	ar3
   00E1 D0 02              1132 	pop	ar2
   00E3 80 DC              1133 	sjmp	00101$
   00E5                    1134 00104$:
   00E5 22                 1135 	ret
                           1136 ;------------------------------------------------------------
                           1137 ;Allocation info for local variables in function 'cons_putsln'
                           1138 ;------------------------------------------------------------
                           1139 ;s                         Allocated to registers r2 r3 r4 
                           1140 ;------------------------------------------------------------
                           1141 ;	radio.c:40: void cons_putsln(const char *s)
                           1142 ;	-----------------------------------------
                           1143 ;	 function cons_putsln
                           1144 ;	-----------------------------------------
   00E6                    1145 _cons_putsln:
                           1146 ;	radio.c:42: cons_puts(s);
   00E6 12 00 BB           1147 	lcall	_cons_puts
                           1148 ;	radio.c:43: cons_puts("\r\n");
   00E9 90 07 EA           1149 	mov	dptr,#__str_0
   00EC 75 F0 80           1150 	mov	b,#0x80
   00EF 02 00 BB           1151 	ljmp	_cons_puts
                           1152 ;------------------------------------------------------------
                           1153 ;Allocation info for local variables in function 'cons_puthex8'
                           1154 ;------------------------------------------------------------
                           1155 ;h                         Allocated to registers r2 
                           1156 ;------------------------------------------------------------
                           1157 ;	radio.c:46: void cons_puthex8(uint8_t h) {
                           1158 ;	-----------------------------------------
                           1159 ;	 function cons_puthex8
                           1160 ;	-----------------------------------------
   00F2                    1161 _cons_puthex8:
   00F2 AA 82              1162 	mov	r2,dpl
                           1163 ;	radio.c:47: cons_putc(nibble_to_char((h & 0xF0)>>4));
   00F4 74 F0              1164 	mov	a,#0xF0
   00F6 5A                 1165 	anl	a,r2
   00F7 C4                 1166 	swap	a
   00F8 54 0F              1167 	anl	a,#0x0f
   00FA F5 82              1168 	mov	dpl,a
   00FC C0 02              1169 	push	ar2
   00FE 12 00 9C           1170 	lcall	_nibble_to_char
   0101 12 00 AF           1171 	lcall	_cons_putc
   0104 D0 02              1172 	pop	ar2
                           1173 ;	radio.c:48: cons_putc(nibble_to_char(h & 0x0F));
   0106 74 0F              1174 	mov	a,#0x0F
   0108 5A                 1175 	anl	a,r2
   0109 F5 82              1176 	mov	dpl,a
   010B 12 00 9C           1177 	lcall	_nibble_to_char
   010E 02 00 AF           1178 	ljmp	_cons_putc
                           1179 ;------------------------------------------------------------
                           1180 ;Allocation info for local variables in function 'cons_puthex16'
                           1181 ;------------------------------------------------------------
                           1182 ;h                         Allocated to registers r2 r3 
                           1183 ;------------------------------------------------------------
                           1184 ;	radio.c:51: void cons_puthex16(uint16_t h)
                           1185 ;	-----------------------------------------
                           1186 ;	 function cons_puthex16
                           1187 ;	-----------------------------------------
   0111                    1188 _cons_puthex16:
   0111 AA 82              1189 	mov	r2,dpl
   0113 AB 83              1190 	mov	r3,dph
                           1191 ;	radio.c:53: cons_putc(nibble_to_char((h & 0xF000)>>12));
   0115 74 F0              1192 	mov	a,#0xF0
   0117 5B                 1193 	anl	a,r3
   0118 C4                 1194 	swap	a
   0119 54 0F              1195 	anl	a,#0x0f
   011B F5 82              1196 	mov	dpl,a
   011D C0 02              1197 	push	ar2
   011F C0 03              1198 	push	ar3
   0121 12 00 9C           1199 	lcall	_nibble_to_char
   0124 12 00 AF           1200 	lcall	_cons_putc
   0127 D0 03              1201 	pop	ar3
                           1202 ;	radio.c:54: cons_putc(nibble_to_char((h & 0x0F00)>>8));
   0129 74 0F              1203 	mov	a,#0x0F
   012B 5B                 1204 	anl	a,r3
   012C F5 82              1205 	mov	dpl,a
   012E C0 03              1206 	push	ar3
   0130 12 00 9C           1207 	lcall	_nibble_to_char
   0133 12 00 AF           1208 	lcall	_cons_putc
   0136 D0 03              1209 	pop	ar3
   0138 D0 02              1210 	pop	ar2
                           1211 ;	radio.c:55: cons_putc(nibble_to_char((h & 0x00F0)>>4));
   013A 74 F0              1212 	mov	a,#0xF0
   013C 5A                 1213 	anl	a,r2
   013D FC                 1214 	mov	r4,a
   013E E4                 1215 	clr	a
   013F C4                 1216 	swap	a
   0140 CC                 1217 	xch	a,r4
   0141 C4                 1218 	swap	a
   0142 54 0F              1219 	anl	a,#0x0f
   0144 6C                 1220 	xrl	a,r4
   0145 CC                 1221 	xch	a,r4
   0146 54 0F              1222 	anl	a,#0x0f
   0148 CC                 1223 	xch	a,r4
   0149 6C                 1224 	xrl	a,r4
   014A CC                 1225 	xch	a,r4
   014B 8C 82              1226 	mov	dpl,r4
   014D C0 02              1227 	push	ar2
   014F C0 03              1228 	push	ar3
   0151 12 00 9C           1229 	lcall	_nibble_to_char
   0154 12 00 AF           1230 	lcall	_cons_putc
   0157 D0 03              1231 	pop	ar3
   0159 D0 02              1232 	pop	ar2
                           1233 ;	radio.c:56: cons_putc(nibble_to_char(h & 0x000F));
   015B 53 02 0F           1234 	anl	ar2,#0x0F
   015E 8A 82              1235 	mov	dpl,r2
   0160 12 00 9C           1236 	lcall	_nibble_to_char
   0163 02 00 AF           1237 	ljmp	_cons_putc
                           1238 ;------------------------------------------------------------
                           1239 ;Allocation info for local variables in function 'convert_rssi'
                           1240 ;------------------------------------------------------------
                           1241 ;rssi_raw                  Allocated to registers r2 
                           1242 ;rssi_dec                  Allocated to registers r2 r3 
                           1243 ;------------------------------------------------------------
                           1244 ;	radio.c:59: int convert_rssi(uint8_t rssi_raw) {
                           1245 ;	-----------------------------------------
                           1246 ;	 function convert_rssi
                           1247 ;	-----------------------------------------
   0166                    1248 _convert_rssi:
   0166 AA 82              1249 	mov	r2,dpl
                           1250 ;	radio.c:60: int rssi_dec = (int) rssi_raw;
   0168 7B 00              1251 	mov	r3,#0x00
                           1252 ;	radio.c:62: if (rssi_dec < 128) {
   016A C3                 1253 	clr	c
   016B EA                 1254 	mov	a,r2
   016C 94 80              1255 	subb	a,#0x80
   016E EB                 1256 	mov	a,r3
   016F 64 80              1257 	xrl	a,#0x80
   0171 94 80              1258 	subb	a,#0x80
   0173 50 1E              1259 	jnc	00102$
                           1260 ;	radio.c:63: return (rssi_dec / 2) - rssi_offset;
   0175 75 1F 02           1261 	mov	__divsint_PARM_2,#0x02
   0178 E4                 1262 	clr	a
   0179 F5 20              1263 	mov	(__divsint_PARM_2 + 1),a
   017B 8A 82              1264 	mov	dpl,r2
   017D 8B 83              1265 	mov	dph,r3
   017F 12 07 AE           1266 	lcall	__divsint
   0182 E5 82              1267 	mov	a,dpl
   0184 85 83 F0           1268 	mov	b,dph
   0187 C3                 1269 	clr	c
   0188 95 0C              1270 	subb	a,_rssi_offset
   018A F5 82              1271 	mov	dpl,a
   018C E5 F0              1272 	mov	a,b
   018E 95 0D              1273 	subb	a,(_rssi_offset + 1)
   0190 F5 83              1274 	mov	dph,a
   0192 22                 1275 	ret
   0193                    1276 00102$:
                           1277 ;	radio.c:66: return ((rssi_dec - 256) / 2) - rssi_offset;
   0193 8A 82              1278 	mov	dpl,r2
   0195 EB                 1279 	mov	a,r3
   0196 24 FF              1280 	add	a,#0xff
   0198 F5 83              1281 	mov	dph,a
   019A 75 1F 02           1282 	mov	__divsint_PARM_2,#0x02
   019D E4                 1283 	clr	a
   019E F5 20              1284 	mov	(__divsint_PARM_2 + 1),a
   01A0 12 07 AE           1285 	lcall	__divsint
   01A3 E5 82              1286 	mov	a,dpl
   01A5 85 83 F0           1287 	mov	b,dph
   01A8 C3                 1288 	clr	c
   01A9 95 0C              1289 	subb	a,_rssi_offset
   01AB F5 82              1290 	mov	dpl,a
   01AD E5 F0              1291 	mov	a,b
   01AF 95 0D              1292 	subb	a,(_rssi_offset + 1)
   01B1 F5 83              1293 	mov	dph,a
   01B3 22                 1294 	ret
                           1295 ;------------------------------------------------------------
                           1296 ;Allocation info for local variables in function 'switchchange'
                           1297 ;------------------------------------------------------------
                           1298 ;prevstate                 Allocated to registers r2 r3 r4 
                           1299 ;------------------------------------------------------------
                           1300 ;	radio.c:70: void switchchange(int *prevstate) {
                           1301 ;	-----------------------------------------
                           1302 ;	 function switchchange
                           1303 ;	-----------------------------------------
   01B4                    1304 _switchchange:
                           1305 ;	radio.c:71: if (P1_6 != *prevstate) {
   01B4 AA 82              1306 	mov	r2,dpl
   01B6 AB 83              1307 	mov	r3,dph
   01B8 AC F0              1308 	mov	r4,b
   01BA 12 07 92           1309 	lcall	__gptrget
   01BD FD                 1310 	mov	r5,a
   01BE A3                 1311 	inc	dptr
   01BF 12 07 92           1312 	lcall	__gptrget
   01C2 FE                 1313 	mov	r6,a
   01C3 A2 96              1314 	mov	c,_P1_6
   01C5 E4                 1315 	clr	a
   01C6 33                 1316 	rlc	a
   01C7 FF                 1317 	mov	r7,a
   01C8 78 00              1318 	mov	r0,#0x00
   01CA B5 05 06           1319 	cjne	a,ar5,00106$
   01CD E8                 1320 	mov	a,r0
   01CE B5 06 02           1321 	cjne	a,ar6,00106$
   01D1 80 14              1322 	sjmp	00102$
   01D3                    1323 00106$:
                           1324 ;	radio.c:72: P1_3 ^= 1;
   01D3 B2 93              1325 	cpl	_P1_3
                           1326 ;	radio.c:73: delay(100); // crap debounce
   01D5 90 00 64           1327 	mov	dptr,#0x0064
   01D8 C0 02              1328 	push	ar2
   01DA C0 03              1329 	push	ar3
   01DC C0 04              1330 	push	ar4
   01DE 12 00 70           1331 	lcall	_delay
   01E1 D0 04              1332 	pop	ar4
   01E3 D0 03              1333 	pop	ar3
   01E5 D0 02              1334 	pop	ar2
   01E7                    1335 00102$:
                           1336 ;	radio.c:75: *prevstate = P1_6;
   01E7 A2 96              1337 	mov	c,_P1_6
   01E9 E4                 1338 	clr	a
   01EA 33                 1339 	rlc	a
   01EB FD                 1340 	mov	r5,a
   01EC 7E 00              1341 	mov	r6,#0x00
   01EE 8A 82              1342 	mov	dpl,r2
   01F0 8B 83              1343 	mov	dph,r3
   01F2 8C F0              1344 	mov	b,r4
   01F4 ED                 1345 	mov	a,r5
   01F5 12 07 50           1346 	lcall	__gptrput
   01F8 A3                 1347 	inc	dptr
   01F9 EE                 1348 	mov	a,r6
   01FA 02 07 50           1349 	ljmp	__gptrput
                           1350 ;------------------------------------------------------------
                           1351 ;Allocation info for local variables in function 'rftxrx_isr'
                           1352 ;------------------------------------------------------------
                           1353 ;------------------------------------------------------------
                           1354 ;	radio.c:78: void rftxrx_isr(void) __interrupt RFTXRX_VECTOR {
                           1355 ;	-----------------------------------------
                           1356 ;	 function rftxrx_isr
                           1357 ;	-----------------------------------------
   01FD                    1358 _rftxrx_isr:
   01FD C0 E0              1359 	push	acc
   01FF C0 82              1360 	push	dpl
   0201 C0 83              1361 	push	dph
   0203 C0 02              1362 	push	ar2
   0205 C0 D0              1363 	push	psw
   0207 75 D0 00           1364 	mov	psw,#0x00
                           1365 ;	radio.c:79: switch (MARCSTATE) {
   020A 90 DF 3B           1366 	mov	dptr,#_MARCSTATE
   020D E0                 1367 	movx	a,@dptr
   020E FA                 1368 	mov	r2,a
   020F BA 0D 02           1369 	cjne	r2,#0x0D,00108$
   0212 80 05              1370 	sjmp	00101$
   0214                    1371 00108$:
                           1372 ;	radio.c:80: case MARC_STATE_RX:
   0214 BA 13 26           1373 	cjne	r2,#0x13,00104$
   0217 80 13              1374 	sjmp	00102$
   0219                    1375 00101$:
                           1376 ;	radio.c:82: packet[packet_index++] = RFD;
   0219 AA 08              1377 	mov	r2,_packet_index
   021B 05 08              1378 	inc	_packet_index
   021D EA                 1379 	mov	a,r2
   021E 24 00              1380 	add	a,#_packet
   0220 F5 82              1381 	mov	dpl,a
   0222 E4                 1382 	clr	a
   0223 34 F0              1383 	addc	a,#(_packet >> 8)
   0225 F5 83              1384 	mov	dph,a
   0227 E5 D9              1385 	mov	a,_RFD
   0229 F0                 1386 	movx	@dptr,a
                           1387 ;	radio.c:83: break;
                           1388 ;	radio.c:84: case MARC_STATE_TX:
   022A 80 11              1389 	sjmp	00104$
   022C                    1390 00102$:
                           1391 ;	radio.c:86: RFD = packet[packet_index++];
   022C AA 08              1392 	mov	r2,_packet_index
   022E 05 08              1393 	inc	_packet_index
   0230 EA                 1394 	mov	a,r2
   0231 24 00              1395 	add	a,#_packet
   0233 F5 82              1396 	mov	dpl,a
   0235 E4                 1397 	clr	a
   0236 34 F0              1398 	addc	a,#(_packet >> 8)
   0238 F5 83              1399 	mov	dph,a
   023A E0                 1400 	movx	a,@dptr
   023B F5 D9              1401 	mov	_RFD,a
                           1402 ;	radio.c:88: } 
   023D                    1403 00104$:
   023D D0 D0              1404 	pop	psw
   023F D0 02              1405 	pop	ar2
   0241 D0 83              1406 	pop	dph
   0243 D0 82              1407 	pop	dpl
   0245 D0 E0              1408 	pop	acc
   0247 32                 1409 	reti
                           1410 ;	eliminated unneeded push/pop b
                           1411 ;------------------------------------------------------------
                           1412 ;Allocation info for local variables in function 'sendpacket'
                           1413 ;------------------------------------------------------------
                           1414 ;------------------------------------------------------------
                           1415 ;	radio.c:91: void sendpacket() {
                           1416 ;	-----------------------------------------
                           1417 ;	 function sendpacket
                           1418 ;	-----------------------------------------
   0248                    1419 _sendpacket:
                           1420 ;	radio.c:92: cons_putsln("Start TX");
   0248 90 07 ED           1421 	mov	dptr,#__str_1
   024B 75 F0 80           1422 	mov	b,#0x80
   024E 12 00 E6           1423 	lcall	_cons_putsln
                           1424 ;	radio.c:94: T3CTL=0xDC;
   0251 75 CB DC           1425 	mov	_T3CTL,#0xDC
                           1426 ;	radio.c:95: T3OVFIF=0; 
   0254 C2 D8              1427 	clr	_T3OVFIF
                           1428 ;	radio.c:96: while (!T3OVFIF);
   0256                    1429 00101$:
   0256 30 D8 FD           1430 	jnb	_T3OVFIF,00101$
                           1431 ;	radio.c:97: T3CTL=0;
   0259 75 CB 00           1432 	mov	_T3CTL,#0x00
                           1433 ;	radio.c:104: packet_index = 0;
   025C 75 08 00           1434 	mov	_packet_index,#0x00
                           1435 ;	radio.c:105: RFST = RFST_STX;
   025F 75 E1 03           1436 	mov	_RFST,#0x03
                           1437 ;	radio.c:106: while (MARCSTATE != MARC_STATE_TX);
   0262                    1438 00104$:
   0262 90 DF 3B           1439 	mov	dptr,#_MARCSTATE
   0265 E0                 1440 	movx	a,@dptr
   0266 FA                 1441 	mov	r2,a
   0267 BA 13 F8           1442 	cjne	r2,#0x13,00104$
                           1443 ;	radio.c:108: while (MARCSTATE != MARC_STATE_IDLE);
   026A                    1444 00107$:
   026A 90 DF 3B           1445 	mov	dptr,#_MARCSTATE
   026D E0                 1446 	movx	a,@dptr
   026E FA                 1447 	mov	r2,a
   026F BA 01 F8           1448 	cjne	r2,#0x01,00107$
                           1449 ;	radio.c:109: RFIF=0;
   0272 75 E9 00           1450 	mov	_RFIF,#0x00
                           1451 ;	radio.c:110: cons_putsln("Done TX");
   0275 90 07 F6           1452 	mov	dptr,#__str_2
   0278 75 F0 80           1453 	mov	b,#0x80
   027B 02 00 E6           1454 	ljmp	_cons_putsln
                           1455 ;------------------------------------------------------------
                           1456 ;Allocation info for local variables in function 'sendllap'
                           1457 ;------------------------------------------------------------
                           1458 ;count                     Allocated with name '_sendllap_PARM_2'
                           1459 ;m                         Allocated to registers r2 r3 r4 
                           1460 ;i                         Allocated to registers r2 r3 
                           1461 ;------------------------------------------------------------
                           1462 ;	radio.c:113: void sendllap(char *m, int count) {
                           1463 ;	-----------------------------------------
                           1464 ;	 function sendllap
                           1465 ;	-----------------------------------------
   027E                    1466 _sendllap:
   027E AA 82              1467 	mov	r2,dpl
   0280 AB 83              1468 	mov	r3,dph
   0282 AC F0              1469 	mov	r4,b
                           1470 ;	radio.c:117: memcpy(packet, preamble, sizeof(preamble)/sizeof(uint8_t));
   0284 75 1F 09           1471 	mov	_memcpy_PARM_2,#_preamble
   0287 75 20 00           1472 	mov	(_memcpy_PARM_2 + 1),#0x00
   028A 75 21 40           1473 	mov	(_memcpy_PARM_2 + 2),#0x40
   028D 75 22 03           1474 	mov	_memcpy_PARM_3,#0x03
   0290 E4                 1475 	clr	a
   0291 F5 23              1476 	mov	(_memcpy_PARM_3 + 1),a
   0293 90 F0 00           1477 	mov	dptr,#_packet
   0296 75 F0 00           1478 	mov	b,#0x00
   0299 C0 02              1479 	push	ar2
   029B C0 03              1480 	push	ar3
   029D C0 04              1481 	push	ar4
   029F 12 06 F8           1482 	lcall	_memcpy
   02A2 D0 04              1483 	pop	ar4
   02A4 D0 03              1484 	pop	ar3
   02A6 D0 02              1485 	pop	ar2
                           1486 ;	radio.c:119: memcpy(packet+sizeof(preamble)/sizeof(uint8_t), m, 12);
   02A8 8A 1F              1487 	mov	_memcpy_PARM_2,r2
   02AA 8B 20              1488 	mov	(_memcpy_PARM_2 + 1),r3
   02AC 8C 21              1489 	mov	(_memcpy_PARM_2 + 2),r4
   02AE 75 22 0C           1490 	mov	_memcpy_PARM_3,#0x0C
   02B1 E4                 1491 	clr	a
   02B2 F5 23              1492 	mov	(_memcpy_PARM_3 + 1),a
   02B4 90 F0 03           1493 	mov	dptr,#(_packet + 0x0003)
   02B7 75 F0 00           1494 	mov	b,#0x00
   02BA 12 06 F8           1495 	lcall	_memcpy
                           1496 ;	radio.c:121: for (i=0; i<count; i++)
   02BD 7A 00              1497 	mov	r2,#0x00
   02BF 7B 00              1498 	mov	r3,#0x00
   02C1                    1499 00101$:
   02C1 C3                 1500 	clr	c
   02C2 EA                 1501 	mov	a,r2
   02C3 95 0E              1502 	subb	a,_sendllap_PARM_2
   02C5 EB                 1503 	mov	a,r3
   02C6 64 80              1504 	xrl	a,#0x80
   02C8 85 0F F0           1505 	mov	b,(_sendllap_PARM_2 + 1)
   02CB 63 F0 80           1506 	xrl	b,#0x80
   02CE 95 F0              1507 	subb	a,b
   02D0 50 12              1508 	jnc	00105$
                           1509 ;	radio.c:122: sendpacket();
   02D2 C0 02              1510 	push	ar2
   02D4 C0 03              1511 	push	ar3
   02D6 12 02 48           1512 	lcall	_sendpacket
   02D9 D0 03              1513 	pop	ar3
   02DB D0 02              1514 	pop	ar2
                           1515 ;	radio.c:121: for (i=0; i<count; i++)
   02DD 0A                 1516 	inc	r2
   02DE BA 00 E0           1517 	cjne	r2,#0x00,00101$
   02E1 0B                 1518 	inc	r3
   02E2 80 DD              1519 	sjmp	00101$
   02E4                    1520 00105$:
   02E4 22                 1521 	ret
                           1522 ;------------------------------------------------------------
                           1523 ;Allocation info for local variables in function 'getpacket'
                           1524 ;------------------------------------------------------------
                           1525 ;llapmsg                   Allocated with name '_getpacket_llapmsg_1_1'
                           1526 ;n                         Allocated to registers r2 r3 
                           1527 ;------------------------------------------------------------
                           1528 ;	radio.c:125: void getpacket() {
                           1529 ;	-----------------------------------------
                           1530 ;	 function getpacket
                           1531 ;	-----------------------------------------
   02E5                    1532 _getpacket:
                           1533 ;	radio.c:127: if (RFIF & RFIF_IRQ_DONE) {
   02E5 E5 E9              1534 	mov	a,_RFIF
   02E7 20 E4 03           1535 	jb	acc.4,00150$
   02EA 02 05 01           1536 	ljmp	00127$
   02ED                    1537 00150$:
                           1538 ;	radio.c:130: RFIF = 0;
   02ED 75 E9 00           1539 	mov	_RFIF,#0x00
                           1540 ;	radio.c:137: cons_putsln("New Packet:");
   02F0 90 07 FE           1541 	mov	dptr,#__str_3
   02F3 75 F0 80           1542 	mov	b,#0x80
   02F6 12 00 E6           1543 	lcall	_cons_putsln
                           1544 ;	radio.c:139: cons_puthex8(packet[0]);
   02F9 90 F0 00           1545 	mov	dptr,#_packet
   02FC E0                 1546 	movx	a,@dptr
   02FD F5 82              1547 	mov	dpl,a
   02FF 12 00 F2           1548 	lcall	_cons_puthex8
                           1549 ;	radio.c:140: cons_putsln("");
   0302 90 08 0A           1550 	mov	dptr,#__str_4
   0305 75 F0 80           1551 	mov	b,#0x80
   0308 12 00 E6           1552 	lcall	_cons_putsln
                           1553 ;	radio.c:142: cons_puthex8(packet[1]);
   030B 90 F0 01           1554 	mov	dptr,#(_packet + 0x0001)
   030E E0                 1555 	movx	a,@dptr
   030F F5 82              1556 	mov	dpl,a
   0311 12 00 F2           1557 	lcall	_cons_puthex8
                           1558 ;	radio.c:143: cons_puthex8(packet[2]);
   0314 90 F0 02           1559 	mov	dptr,#(_packet + 0x0002)
   0317 E0                 1560 	movx	a,@dptr
   0318 F5 82              1561 	mov	dpl,a
   031A 12 00 F2           1562 	lcall	_cons_puthex8
                           1563 ;	radio.c:144: cons_putsln("");
   031D 90 08 0A           1564 	mov	dptr,#__str_4
   0320 75 F0 80           1565 	mov	b,#0x80
   0323 12 00 E6           1566 	lcall	_cons_putsln
                           1567 ;	radio.c:148: while(n < (packet[0]+1)) {
   0326 7A 03              1568 	mov	r2,#0x03
   0328 7B 00              1569 	mov	r3,#0x00
   032A                    1570 00101$:
   032A 90 F0 00           1571 	mov	dptr,#_packet
   032D E0                 1572 	movx	a,@dptr
   032E FC                 1573 	mov	r4,a
   032F 7D 00              1574 	mov	r5,#0x00
   0331 0C                 1575 	inc	r4
   0332 BC 00 01           1576 	cjne	r4,#0x00,00151$
   0335 0D                 1577 	inc	r5
   0336                    1578 00151$:
   0336 C3                 1579 	clr	c
   0337 EA                 1580 	mov	a,r2
   0338 9C                 1581 	subb	a,r4
   0339 EB                 1582 	mov	a,r3
   033A 9D                 1583 	subb	a,r5
   033B 50 35              1584 	jnc	00103$
                           1585 ;	radio.c:149: llapmsg[n-3] = packet[n];
   033D 8A 04              1586 	mov	ar4,r2
   033F EC                 1587 	mov	a,r4
   0340 24 0D              1588 	add	a,#0xfd+_getpacket_llapmsg_1_1
   0342 F8                 1589 	mov	r0,a
   0343 EA                 1590 	mov	a,r2
   0344 24 00              1591 	add	a,#_packet
   0346 F5 82              1592 	mov	dpl,a
   0348 EB                 1593 	mov	a,r3
   0349 34 F0              1594 	addc	a,#(_packet >> 8)
   034B F5 83              1595 	mov	dph,a
   034D E0                 1596 	movx	a,@dptr
   034E F6                 1597 	mov	@r0,a
                           1598 ;	radio.c:150: cons_putc(packet[n++]);
   034F 8A 04              1599 	mov	ar4,r2
   0351 8B 05              1600 	mov	ar5,r3
   0353 0A                 1601 	inc	r2
   0354 BA 00 01           1602 	cjne	r2,#0x00,00153$
   0357 0B                 1603 	inc	r3
   0358                    1604 00153$:
   0358 EC                 1605 	mov	a,r4
   0359 24 00              1606 	add	a,#_packet
   035B F5 82              1607 	mov	dpl,a
   035D ED                 1608 	mov	a,r5
   035E 34 F0              1609 	addc	a,#(_packet >> 8)
   0360 F5 83              1610 	mov	dph,a
   0362 E0                 1611 	movx	a,@dptr
   0363 F5 82              1612 	mov	dpl,a
   0365 C0 02              1613 	push	ar2
   0367 C0 03              1614 	push	ar3
   0369 12 00 AF           1615 	lcall	_cons_putc
   036C D0 03              1616 	pop	ar3
   036E D0 02              1617 	pop	ar2
   0370 80 B8              1618 	sjmp	00101$
   0372                    1619 00103$:
                           1620 ;	radio.c:152: llapmsg[12] = '\0';
   0372 75 1C 00           1621 	mov	(_getpacket_llapmsg_1_1 + 0x000c),#0x00
                           1622 ;	radio.c:154: cons_putsln("");
   0375 90 08 0A           1623 	mov	dptr,#__str_4
   0378 75 F0 80           1624 	mov	b,#0x80
   037B 12 00 E6           1625 	lcall	_cons_putsln
                           1626 ;	radio.c:155: cons_puts("RSSI: ");
   037E 90 08 0B           1627 	mov	dptr,#__str_5
   0381 75 F0 80           1628 	mov	b,#0x80
   0384 12 00 BB           1629 	lcall	_cons_puts
                           1630 ;	radio.c:156: cons_puthex8(RSSI);
   0387 90 DF 3A           1631 	mov	dptr,#_RSSI
   038A E0                 1632 	movx	a,@dptr
   038B F5 82              1633 	mov	dpl,a
   038D 12 00 F2           1634 	lcall	_cons_puthex8
                           1635 ;	radio.c:158: cons_puts(" LQI: ");
   0390 90 08 12           1636 	mov	dptr,#__str_6
   0393 75 F0 80           1637 	mov	b,#0x80
   0396 12 00 BB           1638 	lcall	_cons_puts
                           1639 ;	radio.c:159: cons_puthex8(LQI);
   0399 90 DF 39           1640 	mov	dptr,#_LQI
   039C E0                 1641 	movx	a,@dptr
   039D F5 82              1642 	mov	dpl,a
   039F 12 00 F2           1643 	lcall	_cons_puthex8
                           1644 ;	radio.c:160: cons_putsln("");
   03A2 90 08 0A           1645 	mov	dptr,#__str_4
   03A5 75 F0 80           1646 	mov	b,#0x80
   03A8 12 00 E6           1647 	lcall	_cons_putsln
                           1648 ;	radio.c:162: if (PKTSTATUS & 0x80) {
   03AB 90 DF 3C           1649 	mov	dptr,#_PKTSTATUS
   03AE E0                 1650 	movx	a,@dptr
   03AF FA                 1651 	mov	r2,a
   03B0 30 E7 0B           1652 	jnb	acc.7,00105$
                           1653 ;	radio.c:163: cons_putsln("CRC: OK");
   03B3 90 08 19           1654 	mov	dptr,#__str_7
   03B6 75 F0 80           1655 	mov	b,#0x80
   03B9 12 00 E6           1656 	lcall	_cons_putsln
   03BC 80 09              1657 	sjmp	00106$
   03BE                    1658 00105$:
                           1659 ;	radio.c:166: cons_putsln("CRC: Fail");
   03BE 90 08 21           1660 	mov	dptr,#__str_8
   03C1 75 F0 80           1661 	mov	b,#0x80
   03C4 12 00 E6           1662 	lcall	_cons_putsln
   03C7                    1663 00106$:
                           1664 ;	radio.c:170: if (strncmp(llapmsg, "aLL", 3) == 0) {
   03C7 75 1F 2B           1665 	mov	_strncmp_PARM_2,#__str_9
   03CA 75 20 08           1666 	mov	(_strncmp_PARM_2 + 1),#(__str_9 >> 8)
   03CD 75 21 80           1667 	mov	(_strncmp_PARM_2 + 2),#0x80
   03D0 75 22 03           1668 	mov	_strncmp_PARM_3,#0x03
   03D3 E4                 1669 	clr	a
   03D4 F5 23              1670 	mov	(_strncmp_PARM_3 + 1),a
   03D6 90 00 10           1671 	mov	dptr,#_getpacket_llapmsg_1_1
   03D9 75 F0 40           1672 	mov	b,#0x40
   03DC 12 06 79           1673 	lcall	_strncmp
   03DF E5 82              1674 	mov	a,dpl
   03E1 85 83 F0           1675 	mov	b,dph
   03E4 45 F0              1676 	orl	a,b
   03E6 60 03              1677 	jz	00155$
   03E8 02 05 01           1678 	ljmp	00127$
   03EB                    1679 00155$:
                           1680 ;	radio.c:172: if (strncmp(llapmsg+3, "LEDON----", 9) == 0) {
   03EB 75 1F 2F           1681 	mov	_strncmp_PARM_2,#__str_10
   03EE 75 20 08           1682 	mov	(_strncmp_PARM_2 + 1),#(__str_10 >> 8)
   03F1 75 21 80           1683 	mov	(_strncmp_PARM_2 + 2),#0x80
   03F4 75 22 09           1684 	mov	_strncmp_PARM_3,#0x09
   03F7 E4                 1685 	clr	a
   03F8 F5 23              1686 	mov	(_strncmp_PARM_3 + 1),a
   03FA 90 00 13           1687 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   03FD 75 F0 40           1688 	mov	b,#0x40
   0400 12 06 79           1689 	lcall	_strncmp
   0403 E5 82              1690 	mov	a,dpl
   0405 85 83 F0           1691 	mov	b,dph
   0408 45 F0              1692 	orl	a,b
   040A 70 14              1693 	jnz	00122$
                           1694 ;	radio.c:173: sendllap(llapmsg, 1);
   040C 75 0E 01           1695 	mov	_sendllap_PARM_2,#0x01
   040F E4                 1696 	clr	a
   0410 F5 0F              1697 	mov	(_sendllap_PARM_2 + 1),a
   0412 90 00 10           1698 	mov	dptr,#_getpacket_llapmsg_1_1
   0415 75 F0 40           1699 	mov	b,#0x40
   0418 12 02 7E           1700 	lcall	_sendllap
                           1701 ;	radio.c:174: P1_3 = 1; // turn on
   041B D2 93              1702 	setb	_P1_3
   041D 02 05 01           1703 	ljmp	00127$
   0420                    1704 00122$:
                           1705 ;	radio.c:175: } else if (strncmp(llapmsg+3, "LEDOFF---", 9) == 0) {
   0420 75 1F 39           1706 	mov	_strncmp_PARM_2,#__str_11
   0423 75 20 08           1707 	mov	(_strncmp_PARM_2 + 1),#(__str_11 >> 8)
   0426 75 21 80           1708 	mov	(_strncmp_PARM_2 + 2),#0x80
   0429 75 22 09           1709 	mov	_strncmp_PARM_3,#0x09
   042C E4                 1710 	clr	a
   042D F5 23              1711 	mov	(_strncmp_PARM_3 + 1),a
   042F 90 00 13           1712 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   0432 75 F0 40           1713 	mov	b,#0x40
   0435 12 06 79           1714 	lcall	_strncmp
   0438 E5 82              1715 	mov	a,dpl
   043A 85 83 F0           1716 	mov	b,dph
   043D 45 F0              1717 	orl	a,b
   043F 70 14              1718 	jnz	00119$
                           1719 ;	radio.c:176: sendllap(llapmsg, 1);
   0441 75 0E 01           1720 	mov	_sendllap_PARM_2,#0x01
   0444 E4                 1721 	clr	a
   0445 F5 0F              1722 	mov	(_sendllap_PARM_2 + 1),a
   0447 90 00 10           1723 	mov	dptr,#_getpacket_llapmsg_1_1
   044A 75 F0 40           1724 	mov	b,#0x40
   044D 12 02 7E           1725 	lcall	_sendllap
                           1726 ;	radio.c:177: P1_3 = 0; // turn off
   0450 C2 93              1727 	clr	_P1_3
   0452 02 05 01           1728 	ljmp	00127$
   0455                    1729 00119$:
                           1730 ;	radio.c:178: } else if (strncmp(llapmsg+3, "HELLO----", 9) == 0) {
   0455 75 1F 43           1731 	mov	_strncmp_PARM_2,#__str_12
   0458 75 20 08           1732 	mov	(_strncmp_PARM_2 + 1),#(__str_12 >> 8)
   045B 75 21 80           1733 	mov	(_strncmp_PARM_2 + 2),#0x80
   045E 75 22 09           1734 	mov	_strncmp_PARM_3,#0x09
   0461 E4                 1735 	clr	a
   0462 F5 23              1736 	mov	(_strncmp_PARM_3 + 1),a
   0464 90 00 13           1737 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   0467 75 F0 40           1738 	mov	b,#0x40
   046A 12 06 79           1739 	lcall	_strncmp
   046D E5 82              1740 	mov	a,dpl
   046F 85 83 F0           1741 	mov	b,dph
   0472 45 F0              1742 	orl	a,b
   0474 70 12              1743 	jnz	00116$
                           1744 ;	radio.c:180: sendllap(llapmsg, 1);
   0476 75 0E 01           1745 	mov	_sendllap_PARM_2,#0x01
   0479 E4                 1746 	clr	a
   047A F5 0F              1747 	mov	(_sendllap_PARM_2 + 1),a
   047C 90 00 10           1748 	mov	dptr,#_getpacket_llapmsg_1_1
   047F 75 F0 40           1749 	mov	b,#0x40
   0482 12 02 7E           1750 	lcall	_sendllap
   0485 02 05 01           1751 	ljmp	00127$
   0488                    1752 00116$:
                           1753 ;	radio.c:181: } else if (strncmp(llapmsg+3, "REBOOT---", 9) == 0) {
   0488 75 1F 4D           1754 	mov	_strncmp_PARM_2,#__str_13
   048B 75 20 08           1755 	mov	(_strncmp_PARM_2 + 1),#(__str_13 >> 8)
   048E 75 21 80           1756 	mov	(_strncmp_PARM_2 + 2),#0x80
   0491 75 22 09           1757 	mov	_strncmp_PARM_3,#0x09
   0494 E4                 1758 	clr	a
   0495 F5 23              1759 	mov	(_strncmp_PARM_3 + 1),a
   0497 90 00 13           1760 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   049A 75 F0 40           1761 	mov	b,#0x40
   049D 12 06 79           1762 	lcall	_strncmp
   04A0 E5 82              1763 	mov	a,dpl
   04A2 85 83 F0           1764 	mov	b,dph
   04A5 45 F0              1765 	orl	a,b
   04A7 70 14              1766 	jnz	00113$
                           1767 ;	radio.c:183: sendllap(llapmsg, 1);
   04A9 75 0E 01           1768 	mov	_sendllap_PARM_2,#0x01
   04AC E4                 1769 	clr	a
   04AD F5 0F              1770 	mov	(_sendllap_PARM_2 + 1),a
   04AF 90 00 10           1771 	mov	dptr,#_getpacket_llapmsg_1_1
   04B2 75 F0 40           1772 	mov	b,#0x40
   04B5 12 02 7E           1773 	lcall	_sendllap
                           1774 ;	radio.c:184: __asm LCALL 0x0 __endasm;
   04B8 12 00 00           1775 	 LCALL 0x0 
   04BB 80 44              1776 	sjmp	00127$
   04BD                    1777 00113$:
                           1778 ;	radio.c:185: } else if (strncmp(llapmsg+3, "LED------", 9) == 0) {
   04BD 75 1F 57           1779 	mov	_strncmp_PARM_2,#__str_14
   04C0 75 20 08           1780 	mov	(_strncmp_PARM_2 + 1),#(__str_14 >> 8)
   04C3 75 21 80           1781 	mov	(_strncmp_PARM_2 + 2),#0x80
   04C6 75 22 09           1782 	mov	_strncmp_PARM_3,#0x09
   04C9 E4                 1783 	clr	a
   04CA F5 23              1784 	mov	(_strncmp_PARM_3 + 1),a
   04CC 90 00 13           1785 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   04CF 75 F0 40           1786 	mov	b,#0x40
   04D2 12 06 79           1787 	lcall	_strncmp
   04D5 E5 82              1788 	mov	a,dpl
   04D7 85 83 F0           1789 	mov	b,dph
   04DA 45 F0              1790 	orl	a,b
   04DC 70 23              1791 	jnz	00127$
                           1792 ;	radio.c:187: if (P1_3 == 0) {
   04DE 20 93 11           1793 	jb	_P1_3,00108$
                           1794 ;	radio.c:188: sendllap("aLLLEDOFF---", 1);
   04E1 75 0E 01           1795 	mov	_sendllap_PARM_2,#0x01
   04E4 E4                 1796 	clr	a
   04E5 F5 0F              1797 	mov	(_sendllap_PARM_2 + 1),a
   04E7 90 08 61           1798 	mov	dptr,#__str_15
   04EA 75 F0 80           1799 	mov	b,#0x80
   04ED 12 02 7E           1800 	lcall	_sendllap
   04F0 80 0F              1801 	sjmp	00127$
   04F2                    1802 00108$:
                           1803 ;	radio.c:190: sendllap("aLLLEDON----", 1);
   04F2 75 0E 01           1804 	mov	_sendllap_PARM_2,#0x01
   04F5 E4                 1805 	clr	a
   04F6 F5 0F              1806 	mov	(_sendllap_PARM_2 + 1),a
   04F8 90 08 6E           1807 	mov	dptr,#__str_16
   04FB 75 F0 80           1808 	mov	b,#0x80
   04FE 12 02 7E           1809 	lcall	_sendllap
   0501                    1810 00127$:
                           1811 ;	radio.c:195: if (MARCSTATE != MARC_STATE_RX) {
   0501 90 DF 3B           1812 	mov	dptr,#_MARCSTATE
   0504 E0                 1813 	movx	a,@dptr
   0505 FA                 1814 	mov	r2,a
   0506 BA 0D 01           1815 	cjne	r2,#0x0D,00162$
   0509 22                 1816 	ret
   050A                    1817 00162$:
                           1818 ;	radio.c:196: packet_index = 0;
   050A 75 08 00           1819 	mov	_packet_index,#0x00
                           1820 ;	radio.c:197: RFST = RFST_SRX;
   050D 75 E1 02           1821 	mov	_RFST,#0x02
                           1822 ;	radio.c:198: while (MARCSTATE != MARC_STATE_RX);
   0510                    1823 00128$:
   0510 90 DF 3B           1824 	mov	dptr,#_MARCSTATE
   0513 E0                 1825 	movx	a,@dptr
   0514 FA                 1826 	mov	r2,a
   0515 BA 0D F8           1827 	cjne	r2,#0x0D,00128$
                           1828 ;	radio.c:199: cons_putsln("Waiting to receive...");
   0518 90 08 7B           1829 	mov	dptr,#__str_17
   051B 75 F0 80           1830 	mov	b,#0x80
   051E 02 00 E6           1831 	ljmp	_cons_putsln
                           1832 ;------------------------------------------------------------
                           1833 ;Allocation info for local variables in function 'radio_init'
                           1834 ;------------------------------------------------------------
                           1835 ;------------------------------------------------------------
                           1836 ;	radio.c:203: void radio_init(void) {
                           1837 ;	-----------------------------------------
                           1838 ;	 function radio_init
                           1839 ;	-----------------------------------------
   0521                    1840 _radio_init:
                           1841 ;	radio.c:206: SLEEP &= ~SLEEP_OSC_PD;
   0521 53 BE FB           1842 	anl	_SLEEP,#0xFB
                           1843 ;	radio.c:208: while( !(SLEEP & SLEEP_XOSC_S) ); 
   0524                    1844 00101$:
   0524 E5 BE              1845 	mov	a,_SLEEP
   0526 30 E6 FB           1846 	jnb	acc.6,00101$
                           1847 ;	radio.c:221: (CLKCON & ~(CLKCON_CLKSPD | CLKCON_OSC))
   0529 AA C6              1848 	mov	r2,_CLKCON
   052B 74 B8              1849 	mov	a,#0xB8
   052D 5A                 1850 	anl	a,r2
   052E F5 F0              1851 	mov	b,a
   0530 74 01              1852 	mov	a,#0x01
   0532 45 F0              1853 	orl	a,b
   0534 F5 C6              1854 	mov	_CLKCON,a
                           1855 ;	radio.c:225: while (CLKCON & CLKCON_OSC); 
   0536                    1856 00104$:
   0536 E5 C6              1857 	mov	a,_CLKCON
   0538 20 E6 FB           1858 	jb	acc.6,00104$
                           1859 ;	radio.c:227: SLEEP |= SLEEP_OSC_PD; 
   053B 43 BE 04           1860 	orl	_SLEEP,#0x04
                           1861 ;	radio.c:230: RFST=RFST_SIDLE; // enter idle state
   053E 75 E1 04           1862 	mov	_RFST,#0x04
                           1863 ;	radio.c:232: FREQ0 = 0x24;
   0541 90 DF 0B           1864 	mov	dptr,#_FREQ0
   0544 74 24              1865 	mov	a,#0x24
   0546 F0                 1866 	movx	@dptr,a
                           1867 ;	radio.c:233: FREQ1 = 0x2D;
   0547 90 DF 0A           1868 	mov	dptr,#_FREQ1
   054A 74 2D              1869 	mov	a,#0x2D
   054C F0                 1870 	movx	@dptr,a
                           1871 ;	radio.c:234: FREQ2 = 0x24;
   054D 90 DF 09           1872 	mov	dptr,#_FREQ2
   0550 74 24              1873 	mov	a,#0x24
   0552 F0                 1874 	movx	@dptr,a
                           1875 ;	radio.c:235: PA_TABLE0 = 0xC2;
   0553 90 DF 2E           1876 	mov	dptr,#_PA_TABLE0
   0556 74 C2              1877 	mov	a,#0xC2
   0558 F0                 1878 	movx	@dptr,a
                           1879 ;	radio.c:236: FSCTRL1 = 0x0C; // FSCTRL1 Frequency Synthesizer Control 
   0559 90 DF 07           1880 	mov	dptr,#_FSCTRL1
   055C 74 0C              1881 	mov	a,#0x0C
   055E F0                 1882 	movx	@dptr,a
                           1883 ;	radio.c:237: MDMCFG4 = 0x1D; // MDMCFG4 Modem configuration 
   055F 90 DF 0C           1884 	mov	dptr,#_MDMCFG4
   0562 74 1D              1885 	mov	a,#0x1D
   0564 F0                 1886 	movx	@dptr,a
                           1887 ;	radio.c:238: MDMCFG3 = 0x55; // MDMCFG3 Modem Configuration 
   0565 90 DF 0D           1888 	mov	dptr,#_MDMCFG3
   0568 74 55              1889 	mov	a,#0x55
   056A F0                 1890 	movx	@dptr,a
                           1891 ;	radio.c:239: MDMCFG2 = 0x13; // MDMCFG2 Modem Configuration 
   056B 90 DF 0E           1892 	mov	dptr,#_MDMCFG2
   056E 74 13              1893 	mov	a,#0x13
   0570 F0                 1894 	movx	@dptr,a
                           1895 ;	radio.c:240: DEVIATN = 0x63; // DEVIATN Modem Deviation Setting 
   0571 90 DF 11           1896 	mov	dptr,#_DEVIATN
   0574 74 63              1897 	mov	a,#0x63
   0576 F0                 1898 	movx	@dptr,a
                           1899 ;	radio.c:241: FREND1 = 0xB6; // FREND1 Front End RX Configuration 
   0577 90 DF 1A           1900 	mov	dptr,#_FREND1
   057A 74 B6              1901 	mov	a,#0xB6
   057C F0                 1902 	movx	@dptr,a
                           1903 ;	radio.c:242: FOCCFG = 0x1D; // FOCCFG Frequency Offset Compensation Configuration 
   057D 90 DF 15           1904 	mov	dptr,#_FOCCFG
   0580 74 1D              1905 	mov	a,#0x1D
   0582 F0                 1906 	movx	@dptr,a
                           1907 ;	radio.c:243: BSCFG = 0x1C; // BSCFG Bit Synchronization Configuration 
   0583 90 DF 16           1908 	mov	dptr,#_BSCFG
   0586 74 1C              1909 	mov	a,#0x1C
   0588 F0                 1910 	movx	@dptr,a
                           1911 ;	radio.c:244: AGCCTRL2 = 0xC7; // AGCCTRL2 AGC Control 
   0589 90 DF 17           1912 	mov	dptr,#_AGCCTRL2
   058C 74 C7              1913 	mov	a,#0xC7
   058E F0                 1914 	movx	@dptr,a
                           1915 ;	radio.c:245: AGCCTRL1 = 0x00; // AGCCTRL1 AGC Control 
   058F 90 DF 18           1916 	mov	dptr,#_AGCCTRL1
   0592 E4                 1917 	clr	a
   0593 F0                 1918 	movx	@dptr,a
                           1919 ;	radio.c:246: AGCCTRL0 = 0xB0; // AGCCTRL0 AGC Control 
   0594 90 DF 19           1920 	mov	dptr,#_AGCCTRL0
   0597 74 B0              1921 	mov	a,#0xB0
   0599 F0                 1922 	movx	@dptr,a
                           1923 ;	radio.c:247: FSCAL3 = 0xEA; // FSCAL3 Frequency Synthesizer Calibration 
   059A 90 DF 1C           1924 	mov	dptr,#_FSCAL3
   059D 74 EA              1925 	mov	a,#0xEA
   059F F0                 1926 	movx	@dptr,a
                           1927 ;	radio.c:248: FSCTRL0 = 0x00; // Frequency synthesizer control.
   05A0 90 DF 08           1928 	mov	dptr,#_FSCTRL0
   05A3 E4                 1929 	clr	a
   05A4 F0                 1930 	movx	@dptr,a
                           1931 ;	radio.c:249: FREND0 = 0x10; // Front end TX configuration.
   05A5 90 DF 1B           1932 	mov	dptr,#_FREND0
   05A8 74 10              1933 	mov	a,#0x10
   05AA F0                 1934 	movx	@dptr,a
                           1935 ;	radio.c:250: MCSM0 = 0x18; // Main Radio Control State Machine configuration.
   05AB 90 DF 14           1936 	mov	dptr,#_MCSM0
   05AE 74 18              1937 	mov	a,#0x18
   05B0 F0                 1938 	movx	@dptr,a
                           1939 ;	radio.c:251: FSCAL3 = 0xEA;
   05B1 90 DF 1C           1940 	mov	dptr,#_FSCAL3
   05B4 74 EA              1941 	mov	a,#0xEA
   05B6 F0                 1942 	movx	@dptr,a
                           1943 ;	radio.c:252: FSCAL2 = 0x2A;
   05B7 90 DF 1D           1944 	mov	dptr,#_FSCAL2
   05BA 74 2A              1945 	mov	a,#0x2A
   05BC F0                 1946 	movx	@dptr,a
                           1947 ;	radio.c:253: FSCAL1 = 0x00; // Frequency synthesizer calibration.
   05BD 90 DF 1E           1948 	mov	dptr,#_FSCAL1
   05C0 E4                 1949 	clr	a
   05C1 F0                 1950 	movx	@dptr,a
                           1951 ;	radio.c:254: FSCAL0 = 0x1F; // Frequency synthesizer calibration.
   05C2 90 DF 1F           1952 	mov	dptr,#_FSCAL0
   05C5 74 1F              1953 	mov	a,#0x1F
   05C7 F0                 1954 	movx	@dptr,a
                           1955 ;	radio.c:255: TEST2 = 0x88; // Various test settings.
   05C8 90 DF 23           1956 	mov	dptr,#_TEST2
   05CB 74 88              1957 	mov	a,#0x88
   05CD F0                 1958 	movx	@dptr,a
                           1959 ;	radio.c:256: TEST1 = 0x31; // Various test settings.
   05CE 90 DF 24           1960 	mov	dptr,#_TEST1
   05D1 74 31              1961 	mov	a,#0x31
   05D3 F0                 1962 	movx	@dptr,a
                           1963 ;	radio.c:257: TEST0 = 0x09; // Various test settings.
   05D4 90 DF 25           1964 	mov	dptr,#_TEST0
   05D7 74 09              1965 	mov	a,#0x09
   05D9 F0                 1966 	movx	@dptr,a
                           1967 ;	radio.c:260: MDMCFG1 = 0x23; // calc for 24 MHz
   05DA 90 DF 0F           1968 	mov	dptr,#_MDMCFG1
   05DD 74 23              1969 	mov	a,#0x23
   05DF F0                 1970 	movx	@dptr,a
                           1971 ;	radio.c:261: MDMCFG0 = 0x11; // calc for 24 MHz
   05E0 90 DF 10           1972 	mov	dptr,#_MDMCFG0
   05E3 74 11              1973 	mov	a,#0x11
   05E5 F0                 1974 	movx	@dptr,a
                           1975 ;	radio.c:262: CHANNR = 0x00;
   05E6 90 DF 06           1976 	mov	dptr,#_CHANNR
   05E9 E4                 1977 	clr	a
   05EA F0                 1978 	movx	@dptr,a
                           1979 ;	radio.c:263: MCSM1 = 0x30; // Main Radio Control State Machine configuration.
   05EB 90 DF 13           1980 	mov	dptr,#_MCSM1
   05EE 74 30              1981 	mov	a,#0x30
   05F0 F0                 1982 	movx	@dptr,a
                           1983 ;	radio.c:264: PKTCTRL1 = 0x04; // Packet automation control.
   05F1 90 DF 03           1984 	mov	dptr,#_PKTCTRL1
   05F4 74 04              1985 	mov	a,#0x04
   05F6 F0                 1986 	movx	@dptr,a
                           1987 ;	radio.c:265: PKTCTRL0 = 0x45; // Packet automation control. Data whitening on.
   05F7 90 DF 04           1988 	mov	dptr,#_PKTCTRL0
   05FA 74 45              1989 	mov	a,#0x45
   05FC F0                 1990 	movx	@dptr,a
                           1991 ;	radio.c:266: ADDR = 0x00; // Device address. Not used.
   05FD 90 DF 05           1992 	mov	dptr,#_ADDR
   0600 E4                 1993 	clr	a
   0601 F0                 1994 	movx	@dptr,a
                           1995 ;	radio.c:267: PKTLEN = 0x0F;
   0602 90 DF 02           1996 	mov	dptr,#_PKTLEN
   0605 74 0F              1997 	mov	a,#0x0F
   0607 F0                 1998 	movx	@dptr,a
                           1999 ;	radio.c:268: rssi_offset = 77;
   0608 75 0C 4D           2000 	mov	_rssi_offset,#0x4D
   060B E4                 2001 	clr	a
   060C F5 0D              2002 	mov	(_rssi_offset + 1),a
                           2003 ;	radio.c:269: RFIF = 0;
   060E 75 E9 00           2004 	mov	_RFIF,#0x00
                           2005 ;	radio.c:270: packet_index = 0;
   0611 75 08 00           2006 	mov	_packet_index,#0x00
                           2007 ;	radio.c:272: RFTXRXIF=0;
   0614 C2 89              2008 	clr	_RFTXRXIF
                           2009 ;	radio.c:273: RFTXRXIE=1;
   0616 D2 A8              2010 	setb	_RFTXRXIE
                           2011 ;	radio.c:276: RFST=RFST_SIDLE;
   0618 75 E1 04           2012 	mov	_RFST,#0x04
                           2013 ;	radio.c:277: while(MARCSTATE!=MARC_STATE_IDLE);
   061B                    2014 00107$:
   061B 90 DF 3B           2015 	mov	dptr,#_MARCSTATE
   061E E0                 2016 	movx	a,@dptr
   061F FA                 2017 	mov	r2,a
   0620 BA 01 F8           2018 	cjne	r2,#0x01,00107$
                           2019 ;	radio.c:278: cons_putsln("Radio Started");
   0623 90 08 91           2020 	mov	dptr,#__str_18
   0626 75 F0 80           2021 	mov	b,#0x80
   0629 02 00 E6           2022 	ljmp	_cons_putsln
                           2023 ;------------------------------------------------------------
                           2024 ;Allocation info for local variables in function 'main'
                           2025 ;------------------------------------------------------------
                           2026 ;swstate                   Allocated with name '_main_swstate_1_1'
                           2027 ;------------------------------------------------------------
                           2028 ;	radio.c:281: void main() {
                           2029 ;	-----------------------------------------
                           2030 ;	 function main
                           2031 ;	-----------------------------------------
   062C                    2032 _main:
                           2033 ;	radio.c:286: PERCFG = (PERCFG & ~PERCFG_U0CFG) | PERCFG_U1CFG;
   062C AA F1              2034 	mov	r2,_PERCFG
   062E 74 FE              2035 	mov	a,#0xFE
   0630 5A                 2036 	anl	a,r2
   0631 F5 F0              2037 	mov	b,a
   0633 74 02              2038 	mov	a,#0x02
   0635 45 F0              2039 	orl	a,b
   0637 F5 F1              2040 	mov	_PERCFG,a
                           2041 ;	radio.c:287: P0SEL |= 0x08 | 0x04;
   0639 43 F3 0C           2042 	orl	_P0SEL,#0x0C
                           2043 ;	radio.c:288: U0CSR |= 0x80 | 0x40;
   063C 43 86 C0           2044 	orl	_U0CSR,#0xC0
                           2045 ;	radio.c:290: U0GCR = 13;
   063F 75 C5 0D           2046 	mov	_U0GCR,#0x0D
                           2047 ;	radio.c:291: U0BAUD = 59;
   0642 75 C2 3B           2048 	mov	_U0BAUD,#0x3B
                           2049 ;	radio.c:292: URX0IF = 0;
   0645 C2 8B              2050 	clr	_URX0IF
                           2051 ;	radio.c:295: P1DIR |= 0x08;
   0647 43 FE 08           2052 	orl	_P1DIR,#0x08
                           2053 ;	radio.c:296: P1_3 = 0;
   064A C2 93              2054 	clr	_P1_3
                           2055 ;	radio.c:299: swstate = P1_6;
   064C A2 96              2056 	mov	c,_P1_6
   064E E4                 2057 	clr	a
   064F 33                 2058 	rlc	a
   0650 F5 1D              2059 	mov	_main_swstate_1_1,a
   0652 75 1E 00           2060 	mov	(_main_swstate_1_1 + 1),#0x00
                           2061 ;	radio.c:301: radio_init();
   0655 12 05 21           2062 	lcall	_radio_init
                           2063 ;	radio.c:304: F1 = 1;
   0658 D2 D1              2064 	setb	_F1
                           2065 ;	radio.c:305: EA = 1;
   065A D2 AF              2066 	setb	_EA
                           2067 ;	radio.c:308: sendllap("aLLSTARTING-", 5);
   065C 75 0E 05           2068 	mov	_sendllap_PARM_2,#0x05
   065F E4                 2069 	clr	a
   0660 F5 0F              2070 	mov	(_sendllap_PARM_2 + 1),a
   0662 90 08 9F           2071 	mov	dptr,#__str_19
   0665 75 F0 80           2072 	mov	b,#0x80
   0668 12 02 7E           2073 	lcall	_sendllap
                           2074 ;	radio.c:310: while(1) {
   066B                    2075 00102$:
                           2076 ;	radio.c:312: getpacket();
   066B 12 02 E5           2077 	lcall	_getpacket
                           2078 ;	radio.c:314: switchchange(&swstate);
   066E 90 00 1D           2079 	mov	dptr,#_main_swstate_1_1
   0671 75 F0 40           2080 	mov	b,#0x40
   0674 12 01 B4           2081 	lcall	_switchchange
   0677 80 F2              2082 	sjmp	00102$
                           2083 	.area CSEG    (CODE)
                           2084 	.area CONST   (CODE)
   07EA                    2085 __str_0:
   07EA 0D                 2086 	.db 0x0D
   07EB 0A                 2087 	.db 0x0A
   07EC 00                 2088 	.db 0x00
   07ED                    2089 __str_1:
   07ED 53 74 61 72 74 20  2090 	.ascii "Start TX"
        54 58
   07F5 00                 2091 	.db 0x00
   07F6                    2092 __str_2:
   07F6 44 6F 6E 65 20 54  2093 	.ascii "Done TX"
        58
   07FD 00                 2094 	.db 0x00
   07FE                    2095 __str_3:
   07FE 4E 65 77 20 50 61  2096 	.ascii "New Packet:"
        63 6B 65 74 3A
   0809 00                 2097 	.db 0x00
   080A                    2098 __str_4:
   080A 00                 2099 	.db 0x00
   080B                    2100 __str_5:
   080B 52 53 53 49 3A 20  2101 	.ascii "RSSI: "
   0811 00                 2102 	.db 0x00
   0812                    2103 __str_6:
   0812 20 4C 51 49 3A 20  2104 	.ascii " LQI: "
   0818 00                 2105 	.db 0x00
   0819                    2106 __str_7:
   0819 43 52 43 3A 20 4F  2107 	.ascii "CRC: OK"
        4B
   0820 00                 2108 	.db 0x00
   0821                    2109 __str_8:
   0821 43 52 43 3A 20 46  2110 	.ascii "CRC: Fail"
        61 69 6C
   082A 00                 2111 	.db 0x00
   082B                    2112 __str_9:
   082B 61 4C 4C           2113 	.ascii "aLL"
   082E 00                 2114 	.db 0x00
   082F                    2115 __str_10:
   082F 4C 45 44 4F 4E 2D  2116 	.ascii "LEDON----"
        2D 2D 2D
   0838 00                 2117 	.db 0x00
   0839                    2118 __str_11:
   0839 4C 45 44 4F 46 46  2119 	.ascii "LEDOFF---"
        2D 2D 2D
   0842 00                 2120 	.db 0x00
   0843                    2121 __str_12:
   0843 48 45 4C 4C 4F 2D  2122 	.ascii "HELLO----"
        2D 2D 2D
   084C 00                 2123 	.db 0x00
   084D                    2124 __str_13:
   084D 52 45 42 4F 4F 54  2125 	.ascii "REBOOT---"
        2D 2D 2D
   0856 00                 2126 	.db 0x00
   0857                    2127 __str_14:
   0857 4C 45 44 2D 2D 2D  2128 	.ascii "LED------"
        2D 2D 2D
   0860 00                 2129 	.db 0x00
   0861                    2130 __str_15:
   0861 61 4C 4C 4C 45 44  2131 	.ascii "aLLLEDOFF---"
        4F 46 46 2D 2D 2D
   086D 00                 2132 	.db 0x00
   086E                    2133 __str_16:
   086E 61 4C 4C 4C 45 44  2134 	.ascii "aLLLEDON----"
        4F 4E 2D 2D 2D 2D
   087A 00                 2135 	.db 0x00
   087B                    2136 __str_17:
   087B 57 61 69 74 69 6E  2137 	.ascii "Waiting to receive..."
        67 20 74 6F 20 72
        65 63 65 69 76 65
        2E 2E 2E
   0890 00                 2138 	.db 0x00
   0891                    2139 __str_18:
   0891 52 61 64 69 6F 20  2140 	.ascii "Radio Started"
        53 74 61 72 74 65
        64
   089E 00                 2141 	.db 0x00
   089F                    2142 __str_19:
   089F 61 4C 4C 53 54 41  2143 	.ascii "aLLSTARTING-"
        52 54 49 4E 47 2D
   08AB 00                 2144 	.db 0x00
                           2145 	.area XINIT   (CODE)
                           2146 	.area CABS    (ABS,CODE)
