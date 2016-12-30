                              1 ;--------------------------------------------------------
                              2 ; File Created by SDCC : free open source ANSI-C Compiler
                              3 ; Version 2.9.0 #5416 (Jul  3 2016) (UNIX)
                              4 ; This file was generated Fri Dec 30 15:24:15 2016
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
                            452 	.globl _llapid
                            453 	.globl _rssi_offset
                            454 	.globl _preamble
                            455 	.globl _rftxrx_isr
                            456 ;--------------------------------------------------------
                            457 ; special function registers
                            458 ;--------------------------------------------------------
                            459 	.area RSEG    (DATA)
                    0080    460 _P0	=	0x0080
                    0081    461 _SP	=	0x0081
                    0082    462 _DPL0	=	0x0082
                    0083    463 _DPH0	=	0x0083
                    0084    464 _DPL1	=	0x0084
                    0085    465 _DPH1	=	0x0085
                    0086    466 _U0CSR	=	0x0086
                    0087    467 _PCON	=	0x0087
                    0088    468 _TCON	=	0x0088
                    0089    469 _P0IFG	=	0x0089
                    008A    470 _P1IFG	=	0x008a
                    008B    471 _P2IFG	=	0x008b
                    008C    472 _PICTL	=	0x008c
                    008D    473 _P1IEN	=	0x008d
                    008E    474 __SFR8E	=	0x008e
                    008F    475 _P0INP	=	0x008f
                    0090    476 _P1	=	0x0090
                    0091    477 _RFIM	=	0x0091
                    0092    478 _DPS	=	0x0092
                    0093    479 _MPAGE	=	0x0093
                    0093    480 __XPAGE	=	0x0093
                    0094    481 __SFR94	=	0x0094
                    0095    482 __SFR95	=	0x0095
                    0096    483 __SFR96	=	0x0096
                    0097    484 __SFR97	=	0x0097
                    0098    485 _S0CON	=	0x0098
                    0099    486 __SFR99	=	0x0099
                    009A    487 _IEN2	=	0x009a
                    009B    488 _S1CON	=	0x009b
                    009C    489 _T2CT	=	0x009c
                    009D    490 _T2PR	=	0x009d
                    009E    491 _T2CTL	=	0x009e
                    009F    492 __SFR9F	=	0x009f
                    00A0    493 _P2	=	0x00a0
                    00A1    494 _WORIRQ	=	0x00a1
                    00A2    495 _WORCTRL	=	0x00a2
                    00A3    496 _WOREVT0	=	0x00a3
                    00A4    497 _WOREVT1	=	0x00a4
                    00A5    498 _WORTIME0	=	0x00a5
                    00A6    499 _WORTIME1	=	0x00a6
                    00A7    500 __SFRA7	=	0x00a7
                    00A8    501 _IEN0	=	0x00a8
                    00A9    502 _IP0	=	0x00a9
                    00AA    503 __SFRAA	=	0x00aa
                    00AB    504 _FWT	=	0x00ab
                    00AC    505 _FADDRL	=	0x00ac
                    00AD    506 _FADDRH	=	0x00ad
                    00AE    507 _FCTL	=	0x00ae
                    00AF    508 _FWDATA	=	0x00af
                    00B0    509 __SFRB0	=	0x00b0
                    00B1    510 _ENCDI	=	0x00b1
                    00B2    511 _ENCDO	=	0x00b2
                    00B3    512 _ENCCS	=	0x00b3
                    00B4    513 _ADCCON1	=	0x00b4
                    00B5    514 _ADCCON2	=	0x00b5
                    00B6    515 _ADCCON3	=	0x00b6
                    00B7    516 __SFRB7	=	0x00b7
                    00B8    517 _IEN1	=	0x00b8
                    00B9    518 _IP1	=	0x00b9
                    00BA    519 _ADCL	=	0x00ba
                    00BB    520 _ADCH	=	0x00bb
                    00BC    521 _RNDL	=	0x00bc
                    00BD    522 _RNDH	=	0x00bd
                    00BE    523 _SLEEP	=	0x00be
                    00BF    524 __SFRBF	=	0x00bf
                    00C0    525 _IRCON	=	0x00c0
                    00C1    526 _U0DBUF	=	0x00c1
                    00C2    527 _U0BAUD	=	0x00c2
                    00C3    528 __SFRC3	=	0x00c3
                    00C4    529 _U0UCR	=	0x00c4
                    00C5    530 _U0GCR	=	0x00c5
                    00C6    531 _CLKCON	=	0x00c6
                    00C7    532 _MEMCTR	=	0x00c7
                    00C8    533 __SFRC8	=	0x00c8
                    00C9    534 _WDCTL	=	0x00c9
                    00CA    535 _T3CNT	=	0x00ca
                    00CB    536 _T3CTL	=	0x00cb
                    00CC    537 _T3CCTL0	=	0x00cc
                    00CD    538 _T3CC0	=	0x00cd
                    00CE    539 _T3CCTL1	=	0x00ce
                    00CF    540 _T3CC1	=	0x00cf
                    00D0    541 _PSW	=	0x00d0
                    00D1    542 _DMAIRQ	=	0x00d1
                    00D2    543 _DMA1CFGL	=	0x00d2
                    00D3    544 _DMA1CFGH	=	0x00d3
                    00D4    545 _DMA0CFGL	=	0x00d4
                    00D5    546 _DMA0CFGH	=	0x00d5
                    00D6    547 _DMAARM	=	0x00d6
                    00D7    548 _DMAREQ	=	0x00d7
                    00D8    549 _TIMIF	=	0x00d8
                    00D9    550 _RFD	=	0x00d9
                    00DA    551 _T1CC0L	=	0x00da
                    00DB    552 _T1CC0H	=	0x00db
                    00DC    553 _T1CC1L	=	0x00dc
                    00DD    554 _T1CC1H	=	0x00dd
                    00DE    555 _T1CC2L	=	0x00de
                    00DF    556 _T1CC2H	=	0x00df
                    00E0    557 _ACC	=	0x00e0
                    00E1    558 _RFST	=	0x00e1
                    00E2    559 _T1CNTL	=	0x00e2
                    00E3    560 _T1CNTH	=	0x00e3
                    00E4    561 _T1CTL	=	0x00e4
                    00E5    562 _T1CCTL0	=	0x00e5
                    00E6    563 _T1CCTL1	=	0x00e6
                    00E7    564 _T1CCTL2	=	0x00e7
                    00E8    565 _IRCON2	=	0x00e8
                    00E9    566 _RFIF	=	0x00e9
                    00EA    567 _T4CNT	=	0x00ea
                    00EB    568 _T4CTL	=	0x00eb
                    00EC    569 _T4CCTL0	=	0x00ec
                    00ED    570 _T4CC0	=	0x00ed
                    00EE    571 _T4CCTL1	=	0x00ee
                    00EF    572 _T4CC1	=	0x00ef
                    00F0    573 _B	=	0x00f0
                    00F1    574 _PERCFG	=	0x00f1
                    00F2    575 _ADCCFG	=	0x00f2
                    00F3    576 _P0SEL	=	0x00f3
                    00F4    577 _P1SEL	=	0x00f4
                    00F5    578 _P2SEL	=	0x00f5
                    00F6    579 _P1INP	=	0x00f6
                    00F7    580 _P2INP	=	0x00f7
                    00F8    581 _U1CSR	=	0x00f8
                    00F9    582 _U1DBUF	=	0x00f9
                    00FA    583 _U1BAUD	=	0x00fa
                    00FB    584 _U1UCR	=	0x00fb
                    00FC    585 _U1GCR	=	0x00fc
                    00FD    586 _P0DIR	=	0x00fd
                    00FE    587 _P1DIR	=	0x00fe
                    00FF    588 _P2DIR	=	0x00ff
                            589 ;--------------------------------------------------------
                            590 ; special function bits
                            591 ;--------------------------------------------------------
                            592 	.area RSEG    (DATA)
                    0080    593 _P0_0	=	0x0080
                    0081    594 _P0_1	=	0x0081
                    0082    595 _P0_2	=	0x0082
                    0083    596 _P0_3	=	0x0083
                    0084    597 _P0_4	=	0x0084
                    0085    598 _P0_5	=	0x0085
                    0086    599 _P0_6	=	0x0086
                    0087    600 _P0_7	=	0x0087
                    0088    601 _IT0	=	0x0088
                    0089    602 _RFTXRXIF	=	0x0089
                    008A    603 _IT1	=	0x008a
                    008B    604 _URX0IF	=	0x008b
                    008D    605 _ADCIF	=	0x008d
                    008F    606 _URX1IF	=	0x008f
                    0090    607 _P1_0	=	0x0090
                    0091    608 _P1_1	=	0x0091
                    0092    609 _P1_2	=	0x0092
                    0093    610 _P1_3	=	0x0093
                    0094    611 _P1_4	=	0x0094
                    0095    612 _P1_5	=	0x0095
                    0096    613 _P1_6	=	0x0096
                    0097    614 _P1_7	=	0x0097
                    0098    615 _ENCIF_0	=	0x0098
                    0099    616 _ENCIF_1	=	0x0099
                    00A0    617 _P2_0	=	0x00a0
                    00A1    618 _P2_1	=	0x00a1
                    00A2    619 _P2_2	=	0x00a2
                    00A3    620 _P2_3	=	0x00a3
                    00A4    621 _P2_4	=	0x00a4
                    00A5    622 _P2_5	=	0x00a5
                    00A6    623 _P2_6	=	0x00a6
                    00A7    624 _P2_7	=	0x00a7
                    00A8    625 _RFTXRXIE	=	0x00a8
                    00A9    626 _ADCIE	=	0x00a9
                    00AA    627 _URX0IE	=	0x00aa
                    00AB    628 _URX1IE	=	0x00ab
                    00AC    629 _ENCIE	=	0x00ac
                    00AD    630 _STIE	=	0x00ad
                    00AF    631 _EA	=	0x00af
                    00B8    632 _DMAIE	=	0x00b8
                    00B9    633 _T1IE	=	0x00b9
                    00BA    634 _T2IE	=	0x00ba
                    00BB    635 _T3IE	=	0x00bb
                    00BC    636 _T4IE	=	0x00bc
                    00BD    637 _P0IE	=	0x00bd
                    00C0    638 _DMAIF	=	0x00c0
                    00C1    639 _T1IF	=	0x00c1
                    00C2    640 _T2IF	=	0x00c2
                    00C3    641 _T3IF	=	0x00c3
                    00C4    642 _T4IF	=	0x00c4
                    00C5    643 _P0IF	=	0x00c5
                    00C7    644 _STIF	=	0x00c7
                    00D0    645 _P	=	0x00d0
                    00D1    646 _F1	=	0x00d1
                    00D2    647 _OV	=	0x00d2
                    00D3    648 _RS0	=	0x00d3
                    00D4    649 _RS1	=	0x00d4
                    00D5    650 _F0	=	0x00d5
                    00D6    651 _AC	=	0x00d6
                    00D7    652 _CY	=	0x00d7
                    00D8    653 _T3OVFIF	=	0x00d8
                    00D9    654 _T3CH0IF	=	0x00d9
                    00DA    655 _T3CH1IF	=	0x00da
                    00DB    656 _T4OVFIF	=	0x00db
                    00DC    657 _T4CH0IF	=	0x00dc
                    00DD    658 _T4CH1IF	=	0x00dd
                    00DE    659 _OVFIM	=	0x00de
                    00E0    660 _ACC_0	=	0x00e0
                    00E1    661 _ACC_1	=	0x00e1
                    00E2    662 _ACC_2	=	0x00e2
                    00E3    663 _ACC_3	=	0x00e3
                    00E4    664 _ACC_4	=	0x00e4
                    00E5    665 _ACC_5	=	0x00e5
                    00E6    666 _ACC_6	=	0x00e6
                    00E7    667 _ACC_7	=	0x00e7
                    00E8    668 _P2IF	=	0x00e8
                    00E9    669 _UTX0IF	=	0x00e9
                    00EA    670 _UTX1IF	=	0x00ea
                    00EB    671 _P1IF	=	0x00eb
                    00EC    672 _WDTIF	=	0x00ec
                    00F0    673 _B_0	=	0x00f0
                    00F1    674 _B_1	=	0x00f1
                    00F2    675 _B_2	=	0x00f2
                    00F3    676 _B_3	=	0x00f3
                    00F4    677 _B_4	=	0x00f4
                    00F5    678 _B_5	=	0x00f5
                    00F6    679 _B_6	=	0x00f6
                    00F7    680 _B_7	=	0x00f7
                    00F8    681 _ACTIVE	=	0x00f8
                    00F9    682 _TX_BYTE	=	0x00f9
                    00FA    683 _RX_BYTE	=	0x00fa
                    00FB    684 _ERR	=	0x00fb
                    00FC    685 _FE	=	0x00fc
                    00FD    686 _SLAVE	=	0x00fd
                    00FE    687 _RE	=	0x00fe
                    00FF    688 _MODE	=	0x00ff
                            689 ;--------------------------------------------------------
                            690 ; overlayable register banks
                            691 ;--------------------------------------------------------
                            692 	.area REG_BANK_0	(REL,OVR,DATA)
   0000                     693 	.ds 8
                            694 ;--------------------------------------------------------
                            695 ; internal ram data
                            696 ;--------------------------------------------------------
                            697 	.area DSEG    (DATA)
   0022                     698 _packet_index:
   0022                     699 	.ds 1
   0023                     700 _preamble::
   0023                     701 	.ds 3
   0026                     702 _rssi_offset::
   0026                     703 	.ds 2
   0028                     704 _llapid::
   0028                     705 	.ds 3
   002B                     706 _sendllap_PARM_2:
   002B                     707 	.ds 2
   002D                     708 _getpacket_llapmsg_1_1:
   002D                     709 	.ds 13
   003A                     710 _main_swstate_1_1:
   003A                     711 	.ds 2
                            712 ;--------------------------------------------------------
                            713 ; overlayable items in internal ram 
                            714 ;--------------------------------------------------------
                            715 	.area	OSEG    (OVR,DATA)
                            716 	.area	OSEG    (OVR,DATA)
                            717 	.area	OSEG    (OVR,DATA)
                            718 ;--------------------------------------------------------
                            719 ; Stack segment in internal ram 
                            720 ;--------------------------------------------------------
                            721 	.area	SSEG	(DATA)
   0055                     722 __start__stack:
   0055                     723 	.ds	1
                            724 
                            725 ;--------------------------------------------------------
                            726 ; indirectly addressable internal ram data
                            727 ;--------------------------------------------------------
                            728 	.area ISEG    (DATA)
                            729 ;--------------------------------------------------------
                            730 ; absolute internal ram data
                            731 ;--------------------------------------------------------
                            732 	.area IABS    (ABS,DATA)
                            733 	.area IABS    (ABS,DATA)
                            734 ;--------------------------------------------------------
                            735 ; bit data
                            736 ;--------------------------------------------------------
                            737 	.area BSEG    (BIT)
                            738 ;--------------------------------------------------------
                            739 ; paged external ram data
                            740 ;--------------------------------------------------------
                            741 	.area PSEG    (PAG,XDATA)
                            742 ;--------------------------------------------------------
                            743 ; external ram data
                            744 ;--------------------------------------------------------
                            745 	.area XSEG    (XDATA)
                    DF02    746 _MDMCTRL0H	=	0xdf02
                    DF00    747 _SYNC1	=	0xdf00
                    DF01    748 _SYNC0	=	0xdf01
                    DF02    749 _PKTLEN	=	0xdf02
                    DF03    750 _PKTCTRL1	=	0xdf03
                    DF04    751 _PKTCTRL0	=	0xdf04
                    DF05    752 _ADDR	=	0xdf05
                    DF06    753 _CHANNR	=	0xdf06
                    DF07    754 _FSCTRL1	=	0xdf07
                    DF08    755 _FSCTRL0	=	0xdf08
                    DF09    756 _FREQ2	=	0xdf09
                    DF0A    757 _FREQ1	=	0xdf0a
                    DF0B    758 _FREQ0	=	0xdf0b
                    DF0C    759 _MDMCFG4	=	0xdf0c
                    DF0D    760 _MDMCFG3	=	0xdf0d
                    DF0E    761 _MDMCFG2	=	0xdf0e
                    DF0F    762 _MDMCFG1	=	0xdf0f
                    DF10    763 _MDMCFG0	=	0xdf10
                    DF11    764 _DEVIATN	=	0xdf11
                    DF12    765 _MCSM2	=	0xdf12
                    DF13    766 _MCSM1	=	0xdf13
                    DF14    767 _MCSM0	=	0xdf14
                    DF15    768 _FOCCFG	=	0xdf15
                    DF16    769 _BSCFG	=	0xdf16
                    DF17    770 _AGCCTRL2	=	0xdf17
                    DF18    771 _AGCCTRL1	=	0xdf18
                    DF19    772 _AGCCTRL0	=	0xdf19
                    DF1A    773 _FREND1	=	0xdf1a
                    DF1B    774 _FREND0	=	0xdf1b
                    DF1C    775 _FSCAL3	=	0xdf1c
                    DF1D    776 _FSCAL2	=	0xdf1d
                    DF1E    777 _FSCAL1	=	0xdf1e
                    DF1F    778 _FSCAL0	=	0xdf1f
                    DF20    779 __XREGDF20	=	0xdf20
                    DF21    780 __XREGDF21	=	0xdf21
                    DF22    781 __XREGDF22	=	0xdf22
                    DF23    782 _TEST2	=	0xdf23
                    DF24    783 _TEST1	=	0xdf24
                    DF25    784 _TEST0	=	0xdf25
                    DF26    785 __XREGDF26	=	0xdf26
                    DF27    786 _PA_TABLE7	=	0xdf27
                    DF28    787 _PA_TABLE6	=	0xdf28
                    DF29    788 _PA_TABLE5	=	0xdf29
                    DF2A    789 _PA_TABLE4	=	0xdf2a
                    DF2B    790 _PA_TABLE3	=	0xdf2b
                    DF2C    791 _PA_TABLE2	=	0xdf2c
                    DF2D    792 _PA_TABLE1	=	0xdf2d
                    DF2E    793 _PA_TABLE0	=	0xdf2e
                    DF2F    794 _IOCFG2	=	0xdf2f
                    DF30    795 _IOCFG1	=	0xdf30
                    DF31    796 _IOCFG0	=	0xdf31
                    DF32    797 __XREGDF32	=	0xdf32
                    DF33    798 __XREGDF33	=	0xdf33
                    DF34    799 __XREGDF34	=	0xdf34
                    DF35    800 __XREGDF35	=	0xdf35
                    DF36    801 _PARTNUM	=	0xdf36
                    DF37    802 _VERSION	=	0xdf37
                    DF38    803 _FREQEST	=	0xdf38
                    DF39    804 _LQI	=	0xdf39
                    DF3A    805 _RSSI	=	0xdf3a
                    DF3B    806 _MARCSTATE	=	0xdf3b
                    DF3C    807 _PKTSTATUS	=	0xdf3c
                    DF3D    808 _VCO_VC_DAC	=	0xdf3d
                    DF40    809 _I2SCFG0	=	0xdf40
                    DF41    810 _I2SCFG1	=	0xdf41
                    DF42    811 _I2SDATL	=	0xdf42
                    DF43    812 _I2SDATH	=	0xdf43
                    DF44    813 _I2SWCNT	=	0xdf44
                    DF45    814 _I2SSTAT	=	0xdf45
                    DF46    815 _I2SCLKF0	=	0xdf46
                    DF47    816 _I2SCLKF1	=	0xdf47
                    DF48    817 _I2SCLKF2	=	0xdf48
                    DF80    818 __NA_P0	=	0xdf80
                    DF81    819 __NA_SP	=	0xdf81
                    DF82    820 __NA_DPL0	=	0xdf82
                    DF83    821 __NA_DPH0	=	0xdf83
                    DF84    822 __NA_DPL1	=	0xdf84
                    DF85    823 __NA_DPH1	=	0xdf85
                    DF86    824 _X_U0CSR	=	0xdf86
                    DF87    825 __NA_PCON	=	0xdf87
                    DF88    826 __NA_TCON	=	0xdf88
                    DF89    827 _X_P0IFG	=	0xdf89
                    DF8A    828 _X_P1IFG	=	0xdf8a
                    DF8B    829 _X_P2IFG	=	0xdf8b
                    DF8C    830 _X_PICTL	=	0xdf8c
                    DF8D    831 _X_P1IEN	=	0xdf8d
                    DF8E    832 __X_SFR8E	=	0xdf8e
                    DF8F    833 _X_P0INP	=	0xdf8f
                    DF90    834 __NA_P1	=	0xdf90
                    DF91    835 _X_RFIM	=	0xdf91
                    DF92    836 __NA_DPS	=	0xdf92
                    DF93    837 _X_MPAGE	=	0xdf93
                    DF94    838 __X_SFR94	=	0xdf94
                    DF95    839 __X_SFR95	=	0xdf95
                    DF96    840 __X_SFR96	=	0xdf96
                    DF97    841 __X_SFR97	=	0xdf97
                    DF98    842 __NA_S0CON	=	0xdf98
                    DF99    843 __X_SFR99	=	0xdf99
                    DF9A    844 __NA_IEN2	=	0xdf9a
                    DF9B    845 __NA_S1CON	=	0xdf9b
                    DF9C    846 _X_T2CT	=	0xdf9c
                    DF9D    847 _X_T2PR	=	0xdf9d
                    DF9E    848 _X_T2CTL	=	0xdf9e
                    DF9F    849 __X_SFR9F	=	0xdf9f
                    DFA0    850 __NA_P2	=	0xdfa0
                    DFA1    851 _X_WORIRQ	=	0xdfa1
                    DFA2    852 _X_WORCTRL	=	0xdfa2
                    DFA3    853 _X_WOREVT0	=	0xdfa3
                    DFA4    854 _X_WOREVT1	=	0xdfa4
                    DFA5    855 _X_WORTIME0	=	0xdfa5
                    DFA6    856 _X_WORTIME1	=	0xdfa6
                    DFA7    857 __X_SFRA7	=	0xdfa7
                    DFA8    858 __NA_IEN0	=	0xdfa8
                    DFA9    859 __NA_IP0	=	0xdfa9
                    DFAA    860 __X_SFRAA	=	0xdfaa
                    DFAB    861 _X_FWT	=	0xdfab
                    DFAC    862 _X_FADDRL	=	0xdfac
                    DFAD    863 _X_FADDRH	=	0xdfad
                    DFAE    864 _X_FCTL	=	0xdfae
                    DFAF    865 _X_FWDATA	=	0xdfaf
                    DFB0    866 __X_SFRB0	=	0xdfb0
                    DFB1    867 _X_ENCDI	=	0xdfb1
                    DFB2    868 _X_ENCDO	=	0xdfb2
                    DFB3    869 _X_ENCCS	=	0xdfb3
                    DFB4    870 _X_ADCCON1	=	0xdfb4
                    DFB5    871 _X_ADCCON2	=	0xdfb5
                    DFB6    872 _X_ADCCON3	=	0xdfb6
                    DFB7    873 __X_SFRB7	=	0xdfb7
                    DFB8    874 __NA_IEN1	=	0xdfb8
                    DFB9    875 __NA_IP1	=	0xdfb9
                    DFBA    876 _X_ADCL	=	0xdfba
                    DFBB    877 _X_ADCH	=	0xdfbb
                    DFBC    878 _X_RNDL	=	0xdfbc
                    DFBD    879 _X_RNDH	=	0xdfbd
                    DFBE    880 _X_SLEEP	=	0xdfbe
                    DFBF    881 __X_SFRBF	=	0xdfbf
                    DFC0    882 __NA_IRCON	=	0xdfc0
                    DFC1    883 _X_U0DBUF	=	0xdfc1
                    DFC2    884 _X_U0BAUD	=	0xdfc2
                    DFC3    885 __X_SFRC3	=	0xdfc3
                    DFC4    886 _X_U0UCR	=	0xdfc4
                    DFC5    887 _X_U0GCR	=	0xdfc5
                    DFC6    888 _X_CLKCON	=	0xdfc6
                    DFC7    889 _X_MEMCTR	=	0xdfc7
                    DFC8    890 __X_SFRC8	=	0xdfc8
                    DFC9    891 _X_WDCTL	=	0xdfc9
                    DFCA    892 _X_T3CNT	=	0xdfca
                    DFCB    893 _X_T3CTL	=	0xdfcb
                    DFCC    894 _X_T3CCTL0	=	0xdfcc
                    DFCD    895 _X_T3CC0	=	0xdfcd
                    DFCE    896 _X_T3CCTL1	=	0xdfce
                    DFCF    897 _X_T3CC1	=	0xdfcf
                    DFD0    898 __NA_PSW	=	0xdfd0
                    DFD1    899 _X_DMAIRQ	=	0xdfd1
                    DFD2    900 _X_DMA1CFGL	=	0xdfd2
                    DFD3    901 _X_DMA1CFGH	=	0xdfd3
                    DFD4    902 _X_DMA0CFGL	=	0xdfd4
                    DFD5    903 _X_DMA0CFGH	=	0xdfd5
                    DFD6    904 _X_DMAARM	=	0xdfd6
                    DFD7    905 _X_DMAREQ	=	0xdfd7
                    DFD8    906 _X_TIMIF	=	0xdfd8
                    DFD9    907 _X_RFD	=	0xdfd9
                    DFDA    908 _X_T1CC0L	=	0xdfda
                    DFDB    909 _X_T1CC0H	=	0xdfdb
                    DFDC    910 _X_T1CC1L	=	0xdfdc
                    DFDD    911 _X_T1CC1H	=	0xdfdd
                    DFDE    912 _X_T1CC2L	=	0xdfde
                    DFDF    913 _X_T1CC2H	=	0xdfdf
                    DFE0    914 __NA_ACC	=	0xdfe0
                    DFE1    915 _X_RFST	=	0xdfe1
                    DFE2    916 _X_T1CNTL	=	0xdfe2
                    DFE3    917 _X_T1CNTH	=	0xdfe3
                    DFE4    918 _X_T1CTL	=	0xdfe4
                    DFE5    919 _X_T1CCTL0	=	0xdfe5
                    DFE6    920 _X_T1CCTL1	=	0xdfe6
                    DFE7    921 _X_T1CCTL2	=	0xdfe7
                    DFE8    922 __NA_IRCON2	=	0xdfe8
                    DFE9    923 _X_RFIF	=	0xdfe9
                    DFEA    924 _X_T4CNT	=	0xdfea
                    DFEB    925 _X_T4CTL	=	0xdfeb
                    DFEC    926 _X_T4CCTL0	=	0xdfec
                    DFED    927 _X_T4CC0	=	0xdfed
                    DFEE    928 _X_T4CCTL1	=	0xdfee
                    DFEF    929 _X_T4CC1	=	0xdfef
                    DFF0    930 __NA_B	=	0xdff0
                    DFF1    931 _X_PERCFG	=	0xdff1
                    DFF2    932 _X_ADCCFG	=	0xdff2
                    DFF3    933 _X_P0SEL	=	0xdff3
                    DFF4    934 _X_P1SEL	=	0xdff4
                    DFF5    935 _X_P2SEL	=	0xdff5
                    DFF6    936 _X_P1INP	=	0xdff6
                    DFF7    937 _X_P2INP	=	0xdff7
                    DFF8    938 _X_U1CSR	=	0xdff8
                    DFF9    939 _X_U1DBUF	=	0xdff9
                    DFFA    940 _X_U1BAUD	=	0xdffa
                    DFFB    941 _X_U1UCR	=	0xdffb
                    DFFC    942 _X_U1GCR	=	0xdffc
                    DFFD    943 _X_P0DIR	=	0xdffd
                    DFFE    944 _X_P1DIR	=	0xdffe
                    DFFF    945 _X_P2DIR	=	0xdfff
   F000                     946 _packet:
   F000                     947 	.ds 255
                            948 ;--------------------------------------------------------
                            949 ; absolute external ram data
                            950 ;--------------------------------------------------------
                            951 	.area XABS    (ABS,XDATA)
                            952 ;--------------------------------------------------------
                            953 ; external initialized ram data
                            954 ;--------------------------------------------------------
                            955 	.area XISEG   (XDATA)
                            956 	.area HOME    (CODE)
                            957 	.area GSINIT0 (CODE)
                            958 	.area GSINIT1 (CODE)
                            959 	.area GSINIT2 (CODE)
                            960 	.area GSINIT3 (CODE)
                            961 	.area GSINIT4 (CODE)
                            962 	.area GSINIT5 (CODE)
                            963 	.area GSINIT  (CODE)
                            964 	.area GSFINAL (CODE)
                            965 	.area CSEG    (CODE)
                            966 ;--------------------------------------------------------
                            967 ; interrupt vector 
                            968 ;--------------------------------------------------------
                            969 	.area HOME    (CODE)
   0000                     970 __interrupt_vect:
   0000 02 00 0B            971 	ljmp	__sdcc_gsinit_startup
   0003 02 02 06            972 	ljmp	_rftxrx_isr
                            973 ;--------------------------------------------------------
                            974 ; global & static initialisations
                            975 ;--------------------------------------------------------
                            976 	.area HOME    (CODE)
                            977 	.area GSINIT  (CODE)
                            978 	.area GSFINAL (CODE)
                            979 	.area GSINIT  (CODE)
                            980 	.globl __sdcc_gsinit_startup
                            981 	.globl __sdcc_program_startup
                            982 	.globl __start__stack
                            983 	.globl __mcs51_genXINIT
                            984 	.globl __mcs51_genXRAMCLEAR
                            985 	.globl __mcs51_genRAMCLEAR
                            986 ;	radio.c:12: uint8_t preamble[] = {0x0E, 0x5A, 0xA5};
   0064 75 23 0E            987 	mov	_preamble,#0x0E
   0067 75 24 5A            988 	mov	(_preamble + 0x0001),#0x5A
   006A 75 25 A5            989 	mov	(_preamble + 0x0002),#0xA5
                            990 ;	radio.c:14: char llapid[] = "LA";
   006D 75 28 4C            991 	mov	_llapid,#0x4C
   0070 75 29 41            992 	mov	(_llapid + 0x0001),#0x41
   0073 75 2A 00            993 	mov	(_llapid + 0x0002),#0x00
                            994 	.area GSFINAL (CODE)
   0076 02 00 06            995 	ljmp	__sdcc_program_startup
                            996 ;--------------------------------------------------------
                            997 ; Home
                            998 ;--------------------------------------------------------
                            999 	.area HOME    (CODE)
                           1000 	.area HOME    (CODE)
   0006                    1001 __sdcc_program_startup:
   0006 12 06 46           1002 	lcall	_main
                           1003 ;	return from main will lock up
   0009 80 FE              1004 	sjmp .
                           1005 ;--------------------------------------------------------
                           1006 ; code
                           1007 ;--------------------------------------------------------
                           1008 	.area CSEG    (CODE)
                           1009 ;------------------------------------------------------------
                           1010 ;Allocation info for local variables in function 'delay'
                           1011 ;------------------------------------------------------------
                           1012 ;msec                      Allocated to registers r2 r3 
                           1013 ;i                         Allocated to registers r4 r5 
                           1014 ;j                         Allocated to registers r6 r7 
                           1015 ;------------------------------------------------------------
                           1016 ;	radio.c:16: void delay(int msec) {
                           1017 ;	-----------------------------------------
                           1018 ;	 function delay
                           1019 ;	-----------------------------------------
   0079                    1020 _delay:
                    0002   1021 	ar2 = 0x02
                    0003   1022 	ar3 = 0x03
                    0004   1023 	ar4 = 0x04
                    0005   1024 	ar5 = 0x05
                    0006   1025 	ar6 = 0x06
                    0007   1026 	ar7 = 0x07
                    0000   1027 	ar0 = 0x00
                    0001   1028 	ar1 = 0x01
   0079 AA 82              1029 	mov	r2,dpl
   007B AB 83              1030 	mov	r3,dph
                           1031 ;	radio.c:19: for (i=0; i<msec; i++)
   007D 7C 00              1032 	mov	r4,#0x00
   007F 7D 00              1033 	mov	r5,#0x00
   0081                    1034 00104$:
   0081 C3                 1035 	clr	c
   0082 EC                 1036 	mov	a,r4
   0083 9A                 1037 	subb	a,r2
   0084 ED                 1038 	mov	a,r5
   0085 64 80              1039 	xrl	a,#0x80
   0087 8B F0              1040 	mov	b,r3
   0089 63 F0 80           1041 	xrl	b,#0x80
   008C 95 F0              1042 	subb	a,b
   008E 50 14              1043 	jnc	00108$
                           1044 ;	radio.c:20: for (j=0; j<1000; j++);
   0090 7E E8              1045 	mov	r6,#0xE8
   0092 7F 03              1046 	mov	r7,#0x03
   0094                    1047 00103$:
   0094 1E                 1048 	dec	r6
   0095 BE FF 01           1049 	cjne	r6,#0xff,00117$
   0098 1F                 1050 	dec	r7
   0099                    1051 00117$:
   0099 EE                 1052 	mov	a,r6
   009A 4F                 1053 	orl	a,r7
   009B 70 F7              1054 	jnz	00103$
                           1055 ;	radio.c:19: for (i=0; i<msec; i++)
   009D 0C                 1056 	inc	r4
   009E BC 00 E0           1057 	cjne	r4,#0x00,00104$
   00A1 0D                 1058 	inc	r5
   00A2 80 DD              1059 	sjmp	00104$
   00A4                    1060 00108$:
   00A4 22                 1061 	ret
                           1062 ;------------------------------------------------------------
                           1063 ;Allocation info for local variables in function 'nibble_to_char'
                           1064 ;------------------------------------------------------------
                           1065 ;nibble                    Allocated to registers r2 
                           1066 ;------------------------------------------------------------
                           1067 ;	radio.c:23: char nibble_to_char(uint8_t nibble) {
                           1068 ;	-----------------------------------------
                           1069 ;	 function nibble_to_char
                           1070 ;	-----------------------------------------
   00A5                    1071 _nibble_to_char:
   00A5 AA 82              1072 	mov	r2,dpl
                           1073 ;	radio.c:24: if (nibble < 0xA)
   00A7 BA 0A 00           1074 	cjne	r2,#0x0A,00106$
   00AA                    1075 00106$:
   00AA 50 06              1076 	jnc	00102$
                           1077 ;	radio.c:25: return nibble + '0';
   00AC 74 30              1078 	mov	a,#0x30
   00AE 2A                 1079 	add	a,r2
   00AF F5 82              1080 	mov	dpl,a
   00B1 22                 1081 	ret
   00B2                    1082 00102$:
                           1083 ;	radio.c:26: return nibble - 0xA + 'A';
   00B2 74 37              1084 	mov	a,#0x37
   00B4 2A                 1085 	add	a,r2
   00B5 F5 82              1086 	mov	dpl,a
   00B7 22                 1087 	ret
                           1088 ;------------------------------------------------------------
                           1089 ;Allocation info for local variables in function 'cons_putc'
                           1090 ;------------------------------------------------------------
                           1091 ;ch                        Allocated to registers 
                           1092 ;------------------------------------------------------------
                           1093 ;	radio.c:29: void cons_putc(uint8_t ch) {
                           1094 ;	-----------------------------------------
                           1095 ;	 function cons_putc
                           1096 ;	-----------------------------------------
   00B8                    1097 _cons_putc:
   00B8 85 82 C1           1098 	mov	_U0DBUF,dpl
                           1099 ;	radio.c:31: while(!(U0CSR & U0CSR_TX_BYTE)); // wait for byte to be transmitted                                                                     
   00BB                    1100 00101$:
   00BB E5 86              1101 	mov	a,_U0CSR
   00BD 30 E1 FB           1102 	jnb	acc.1,00101$
                           1103 ;	radio.c:32: U0CSR &= ~U0CSR_TX_BYTE;         // Clear transmit byte status                                                                          
   00C0 53 86 FD           1104 	anl	_U0CSR,#0xFD
   00C3 22                 1105 	ret
                           1106 ;------------------------------------------------------------
                           1107 ;Allocation info for local variables in function 'cons_puts'
                           1108 ;------------------------------------------------------------
                           1109 ;s                         Allocated to registers r2 r3 r4 
                           1110 ;------------------------------------------------------------
                           1111 ;	radio.c:35: void cons_puts(const char *s)
                           1112 ;	-----------------------------------------
                           1113 ;	 function cons_puts
                           1114 ;	-----------------------------------------
   00C4                    1115 _cons_puts:
   00C4 AA 82              1116 	mov	r2,dpl
   00C6 AB 83              1117 	mov	r3,dph
   00C8 AC F0              1118 	mov	r4,b
                           1119 ;	radio.c:37: while(0 != *s)
   00CA                    1120 00101$:
   00CA 8A 82              1121 	mov	dpl,r2
   00CC 8B 83              1122 	mov	dph,r3
   00CE 8C F0              1123 	mov	b,r4
   00D0 12 0D D5           1124 	lcall	__gptrget
   00D3 FD                 1125 	mov	r5,a
   00D4 60 18              1126 	jz	00104$
                           1127 ;	radio.c:38: cons_putc((uint8_t)(*s++));
   00D6 8D 82              1128 	mov	dpl,r5
   00D8 0A                 1129 	inc	r2
   00D9 BA 00 01           1130 	cjne	r2,#0x00,00110$
   00DC 0B                 1131 	inc	r3
   00DD                    1132 00110$:
   00DD C0 02              1133 	push	ar2
   00DF C0 03              1134 	push	ar3
   00E1 C0 04              1135 	push	ar4
   00E3 12 00 B8           1136 	lcall	_cons_putc
   00E6 D0 04              1137 	pop	ar4
   00E8 D0 03              1138 	pop	ar3
   00EA D0 02              1139 	pop	ar2
   00EC 80 DC              1140 	sjmp	00101$
   00EE                    1141 00104$:
   00EE 22                 1142 	ret
                           1143 ;------------------------------------------------------------
                           1144 ;Allocation info for local variables in function 'cons_putsln'
                           1145 ;------------------------------------------------------------
                           1146 ;s                         Allocated to registers r2 r3 r4 
                           1147 ;------------------------------------------------------------
                           1148 ;	radio.c:41: void cons_putsln(const char *s)
                           1149 ;	-----------------------------------------
                           1150 ;	 function cons_putsln
                           1151 ;	-----------------------------------------
   00EF                    1152 _cons_putsln:
                           1153 ;	radio.c:43: cons_puts(s);
   00EF 12 00 C4           1154 	lcall	_cons_puts
                           1155 ;	radio.c:44: cons_puts("\r\n");
   00F2 90 0E 2D           1156 	mov	dptr,#__str_0
   00F5 75 F0 80           1157 	mov	b,#0x80
   00F8 02 00 C4           1158 	ljmp	_cons_puts
                           1159 ;------------------------------------------------------------
                           1160 ;Allocation info for local variables in function 'cons_puthex8'
                           1161 ;------------------------------------------------------------
                           1162 ;h                         Allocated to registers r2 
                           1163 ;------------------------------------------------------------
                           1164 ;	radio.c:47: void cons_puthex8(uint8_t h) {
                           1165 ;	-----------------------------------------
                           1166 ;	 function cons_puthex8
                           1167 ;	-----------------------------------------
   00FB                    1168 _cons_puthex8:
   00FB AA 82              1169 	mov	r2,dpl
                           1170 ;	radio.c:48: cons_putc(nibble_to_char((h & 0xF0)>>4));
   00FD 74 F0              1171 	mov	a,#0xF0
   00FF 5A                 1172 	anl	a,r2
   0100 C4                 1173 	swap	a
   0101 54 0F              1174 	anl	a,#0x0f
   0103 F5 82              1175 	mov	dpl,a
   0105 C0 02              1176 	push	ar2
   0107 12 00 A5           1177 	lcall	_nibble_to_char
   010A 12 00 B8           1178 	lcall	_cons_putc
   010D D0 02              1179 	pop	ar2
                           1180 ;	radio.c:49: cons_putc(nibble_to_char(h & 0x0F));
   010F 74 0F              1181 	mov	a,#0x0F
   0111 5A                 1182 	anl	a,r2
   0112 F5 82              1183 	mov	dpl,a
   0114 12 00 A5           1184 	lcall	_nibble_to_char
   0117 02 00 B8           1185 	ljmp	_cons_putc
                           1186 ;------------------------------------------------------------
                           1187 ;Allocation info for local variables in function 'cons_puthex16'
                           1188 ;------------------------------------------------------------
                           1189 ;h                         Allocated to registers r2 r3 
                           1190 ;------------------------------------------------------------
                           1191 ;	radio.c:52: void cons_puthex16(uint16_t h)
                           1192 ;	-----------------------------------------
                           1193 ;	 function cons_puthex16
                           1194 ;	-----------------------------------------
   011A                    1195 _cons_puthex16:
   011A AA 82              1196 	mov	r2,dpl
   011C AB 83              1197 	mov	r3,dph
                           1198 ;	radio.c:54: cons_putc(nibble_to_char((h & 0xF000)>>12));
   011E 74 F0              1199 	mov	a,#0xF0
   0120 5B                 1200 	anl	a,r3
   0121 C4                 1201 	swap	a
   0122 54 0F              1202 	anl	a,#0x0f
   0124 F5 82              1203 	mov	dpl,a
   0126 C0 02              1204 	push	ar2
   0128 C0 03              1205 	push	ar3
   012A 12 00 A5           1206 	lcall	_nibble_to_char
   012D 12 00 B8           1207 	lcall	_cons_putc
   0130 D0 03              1208 	pop	ar3
                           1209 ;	radio.c:55: cons_putc(nibble_to_char((h & 0x0F00)>>8));
   0132 74 0F              1210 	mov	a,#0x0F
   0134 5B                 1211 	anl	a,r3
   0135 F5 82              1212 	mov	dpl,a
   0137 C0 03              1213 	push	ar3
   0139 12 00 A5           1214 	lcall	_nibble_to_char
   013C 12 00 B8           1215 	lcall	_cons_putc
   013F D0 03              1216 	pop	ar3
   0141 D0 02              1217 	pop	ar2
                           1218 ;	radio.c:56: cons_putc(nibble_to_char((h & 0x00F0)>>4));
   0143 74 F0              1219 	mov	a,#0xF0
   0145 5A                 1220 	anl	a,r2
   0146 FC                 1221 	mov	r4,a
   0147 E4                 1222 	clr	a
   0148 C4                 1223 	swap	a
   0149 CC                 1224 	xch	a,r4
   014A C4                 1225 	swap	a
   014B 54 0F              1226 	anl	a,#0x0f
   014D 6C                 1227 	xrl	a,r4
   014E CC                 1228 	xch	a,r4
   014F 54 0F              1229 	anl	a,#0x0f
   0151 CC                 1230 	xch	a,r4
   0152 6C                 1231 	xrl	a,r4
   0153 CC                 1232 	xch	a,r4
   0154 8C 82              1233 	mov	dpl,r4
   0156 C0 02              1234 	push	ar2
   0158 C0 03              1235 	push	ar3
   015A 12 00 A5           1236 	lcall	_nibble_to_char
   015D 12 00 B8           1237 	lcall	_cons_putc
   0160 D0 03              1238 	pop	ar3
   0162 D0 02              1239 	pop	ar2
                           1240 ;	radio.c:57: cons_putc(nibble_to_char(h & 0x000F));
   0164 53 02 0F           1241 	anl	ar2,#0x0F
   0167 8A 82              1242 	mov	dpl,r2
   0169 12 00 A5           1243 	lcall	_nibble_to_char
   016C 02 00 B8           1244 	ljmp	_cons_putc
                           1245 ;------------------------------------------------------------
                           1246 ;Allocation info for local variables in function 'convert_rssi'
                           1247 ;------------------------------------------------------------
                           1248 ;rssi_raw                  Allocated to registers r2 
                           1249 ;rssi_dec                  Allocated to registers r2 r3 
                           1250 ;------------------------------------------------------------
                           1251 ;	radio.c:60: int convert_rssi(uint8_t rssi_raw) {
                           1252 ;	-----------------------------------------
                           1253 ;	 function convert_rssi
                           1254 ;	-----------------------------------------
   016F                    1255 _convert_rssi:
   016F AA 82              1256 	mov	r2,dpl
                           1257 ;	radio.c:61: int rssi_dec = (int) rssi_raw;
   0171 7B 00              1258 	mov	r3,#0x00
                           1259 ;	radio.c:63: if (rssi_dec < 128) {
   0173 C3                 1260 	clr	c
   0174 EA                 1261 	mov	a,r2
   0175 94 80              1262 	subb	a,#0x80
   0177 EB                 1263 	mov	a,r3
   0178 64 80              1264 	xrl	a,#0x80
   017A 94 80              1265 	subb	a,#0x80
   017C 50 1E              1266 	jnc	00102$
                           1267 ;	radio.c:64: return (rssi_dec / 2) - rssi_offset;
   017E 75 10 02           1268 	mov	__divsint_PARM_2,#0x02
   0181 E4                 1269 	clr	a
   0182 F5 11              1270 	mov	(__divsint_PARM_2 + 1),a
   0184 8A 82              1271 	mov	dpl,r2
   0186 8B 83              1272 	mov	dph,r3
   0188 12 0D F1           1273 	lcall	__divsint
   018B E5 82              1274 	mov	a,dpl
   018D 85 83 F0           1275 	mov	b,dph
   0190 C3                 1276 	clr	c
   0191 95 26              1277 	subb	a,_rssi_offset
   0193 F5 82              1278 	mov	dpl,a
   0195 E5 F0              1279 	mov	a,b
   0197 95 27              1280 	subb	a,(_rssi_offset + 1)
   0199 F5 83              1281 	mov	dph,a
   019B 22                 1282 	ret
   019C                    1283 00102$:
                           1284 ;	radio.c:67: return ((rssi_dec - 256) / 2) - rssi_offset;
   019C 8A 82              1285 	mov	dpl,r2
   019E EB                 1286 	mov	a,r3
   019F 24 FF              1287 	add	a,#0xff
   01A1 F5 83              1288 	mov	dph,a
   01A3 75 10 02           1289 	mov	__divsint_PARM_2,#0x02
   01A6 E4                 1290 	clr	a
   01A7 F5 11              1291 	mov	(__divsint_PARM_2 + 1),a
   01A9 12 0D F1           1292 	lcall	__divsint
   01AC E5 82              1293 	mov	a,dpl
   01AE 85 83 F0           1294 	mov	b,dph
   01B1 C3                 1295 	clr	c
   01B2 95 26              1296 	subb	a,_rssi_offset
   01B4 F5 82              1297 	mov	dpl,a
   01B6 E5 F0              1298 	mov	a,b
   01B8 95 27              1299 	subb	a,(_rssi_offset + 1)
   01BA F5 83              1300 	mov	dph,a
   01BC 22                 1301 	ret
                           1302 ;------------------------------------------------------------
                           1303 ;Allocation info for local variables in function 'switchchange'
                           1304 ;------------------------------------------------------------
                           1305 ;prevstate                 Allocated to registers r2 r3 r4 
                           1306 ;------------------------------------------------------------
                           1307 ;	radio.c:71: void switchchange(int *prevstate) {
                           1308 ;	-----------------------------------------
                           1309 ;	 function switchchange
                           1310 ;	-----------------------------------------
   01BD                    1311 _switchchange:
                           1312 ;	radio.c:72: if (P1_6 != *prevstate) {
   01BD AA 82              1313 	mov	r2,dpl
   01BF AB 83              1314 	mov	r3,dph
   01C1 AC F0              1315 	mov	r4,b
   01C3 12 0D D5           1316 	lcall	__gptrget
   01C6 FD                 1317 	mov	r5,a
   01C7 A3                 1318 	inc	dptr
   01C8 12 0D D5           1319 	lcall	__gptrget
   01CB FE                 1320 	mov	r6,a
   01CC A2 96              1321 	mov	c,_P1_6
   01CE E4                 1322 	clr	a
   01CF 33                 1323 	rlc	a
   01D0 FF                 1324 	mov	r7,a
   01D1 78 00              1325 	mov	r0,#0x00
   01D3 B5 05 06           1326 	cjne	a,ar5,00106$
   01D6 E8                 1327 	mov	a,r0
   01D7 B5 06 02           1328 	cjne	a,ar6,00106$
   01DA 80 14              1329 	sjmp	00102$
   01DC                    1330 00106$:
                           1331 ;	radio.c:73: P1_3 ^= 1;
   01DC B2 93              1332 	cpl	_P1_3
                           1333 ;	radio.c:74: delay(100); // crap debounce
   01DE 90 00 64           1334 	mov	dptr,#0x0064
   01E1 C0 02              1335 	push	ar2
   01E3 C0 03              1336 	push	ar3
   01E5 C0 04              1337 	push	ar4
   01E7 12 00 79           1338 	lcall	_delay
   01EA D0 04              1339 	pop	ar4
   01EC D0 03              1340 	pop	ar3
   01EE D0 02              1341 	pop	ar2
   01F0                    1342 00102$:
                           1343 ;	radio.c:76: *prevstate = P1_6;
   01F0 A2 96              1344 	mov	c,_P1_6
   01F2 E4                 1345 	clr	a
   01F3 33                 1346 	rlc	a
   01F4 FD                 1347 	mov	r5,a
   01F5 7E 00              1348 	mov	r6,#0x00
   01F7 8A 82              1349 	mov	dpl,r2
   01F9 8B 83              1350 	mov	dph,r3
   01FB 8C F0              1351 	mov	b,r4
   01FD ED                 1352 	mov	a,r5
   01FE 12 07 12           1353 	lcall	__gptrput
   0201 A3                 1354 	inc	dptr
   0202 EE                 1355 	mov	a,r6
   0203 02 07 12           1356 	ljmp	__gptrput
                           1357 ;------------------------------------------------------------
                           1358 ;Allocation info for local variables in function 'rftxrx_isr'
                           1359 ;------------------------------------------------------------
                           1360 ;------------------------------------------------------------
                           1361 ;	radio.c:79: void rftxrx_isr(void) __interrupt RFTXRX_VECTOR {
                           1362 ;	-----------------------------------------
                           1363 ;	 function rftxrx_isr
                           1364 ;	-----------------------------------------
   0206                    1365 _rftxrx_isr:
   0206 C0 E0              1366 	push	acc
   0208 C0 82              1367 	push	dpl
   020A C0 83              1368 	push	dph
   020C C0 02              1369 	push	ar2
   020E C0 D0              1370 	push	psw
   0210 75 D0 00           1371 	mov	psw,#0x00
                           1372 ;	radio.c:80: switch (MARCSTATE) {
   0213 90 DF 3B           1373 	mov	dptr,#_MARCSTATE
   0216 E0                 1374 	movx	a,@dptr
   0217 FA                 1375 	mov	r2,a
   0218 BA 0D 02           1376 	cjne	r2,#0x0D,00108$
   021B 80 05              1377 	sjmp	00101$
   021D                    1378 00108$:
                           1379 ;	radio.c:81: case MARC_STATE_RX:
   021D BA 13 26           1380 	cjne	r2,#0x13,00104$
   0220 80 13              1381 	sjmp	00102$
   0222                    1382 00101$:
                           1383 ;	radio.c:83: packet[packet_index++] = RFD;
   0222 AA 22              1384 	mov	r2,_packet_index
   0224 05 22              1385 	inc	_packet_index
   0226 EA                 1386 	mov	a,r2
   0227 24 00              1387 	add	a,#_packet
   0229 F5 82              1388 	mov	dpl,a
   022B E4                 1389 	clr	a
   022C 34 F0              1390 	addc	a,#(_packet >> 8)
   022E F5 83              1391 	mov	dph,a
   0230 E5 D9              1392 	mov	a,_RFD
   0232 F0                 1393 	movx	@dptr,a
                           1394 ;	radio.c:84: break;
                           1395 ;	radio.c:85: case MARC_STATE_TX:
   0233 80 11              1396 	sjmp	00104$
   0235                    1397 00102$:
                           1398 ;	radio.c:87: RFD = packet[packet_index++];
   0235 AA 22              1399 	mov	r2,_packet_index
   0237 05 22              1400 	inc	_packet_index
   0239 EA                 1401 	mov	a,r2
   023A 24 00              1402 	add	a,#_packet
   023C F5 82              1403 	mov	dpl,a
   023E E4                 1404 	clr	a
   023F 34 F0              1405 	addc	a,#(_packet >> 8)
   0241 F5 83              1406 	mov	dph,a
   0243 E0                 1407 	movx	a,@dptr
   0244 F5 D9              1408 	mov	_RFD,a
                           1409 ;	radio.c:89: } 
   0246                    1410 00104$:
   0246 D0 D0              1411 	pop	psw
   0248 D0 02              1412 	pop	ar2
   024A D0 83              1413 	pop	dph
   024C D0 82              1414 	pop	dpl
   024E D0 E0              1415 	pop	acc
   0250 32                 1416 	reti
                           1417 ;	eliminated unneeded push/pop b
                           1418 ;------------------------------------------------------------
                           1419 ;Allocation info for local variables in function 'sendpacket'
                           1420 ;------------------------------------------------------------
                           1421 ;------------------------------------------------------------
                           1422 ;	radio.c:92: void sendpacket() {
                           1423 ;	-----------------------------------------
                           1424 ;	 function sendpacket
                           1425 ;	-----------------------------------------
   0251                    1426 _sendpacket:
                           1427 ;	radio.c:93: cons_putsln("Start TX");
   0251 90 0E 30           1428 	mov	dptr,#__str_1
   0254 75 F0 80           1429 	mov	b,#0x80
   0257 12 00 EF           1430 	lcall	_cons_putsln
                           1431 ;	radio.c:95: T3CTL=0xDC;
   025A 75 CB DC           1432 	mov	_T3CTL,#0xDC
                           1433 ;	radio.c:96: T3OVFIF=0; 
   025D C2 D8              1434 	clr	_T3OVFIF
                           1435 ;	radio.c:97: while (!T3OVFIF);
   025F                    1436 00101$:
   025F 30 D8 FD           1437 	jnb	_T3OVFIF,00101$
                           1438 ;	radio.c:98: T3CTL=0;
   0262 75 CB 00           1439 	mov	_T3CTL,#0x00
                           1440 ;	radio.c:105: packet_index = 0;
   0265 75 22 00           1441 	mov	_packet_index,#0x00
                           1442 ;	radio.c:106: RFST = RFST_STX;
   0268 75 E1 03           1443 	mov	_RFST,#0x03
                           1444 ;	radio.c:107: while (MARCSTATE != MARC_STATE_TX);
   026B                    1445 00104$:
   026B 90 DF 3B           1446 	mov	dptr,#_MARCSTATE
   026E E0                 1447 	movx	a,@dptr
   026F FA                 1448 	mov	r2,a
   0270 BA 13 F8           1449 	cjne	r2,#0x13,00104$
                           1450 ;	radio.c:109: while (MARCSTATE != MARC_STATE_IDLE);
   0273                    1451 00107$:
   0273 90 DF 3B           1452 	mov	dptr,#_MARCSTATE
   0276 E0                 1453 	movx	a,@dptr
   0277 FA                 1454 	mov	r2,a
   0278 BA 01 F8           1455 	cjne	r2,#0x01,00107$
                           1456 ;	radio.c:110: RFIF=0;
   027B 75 E9 00           1457 	mov	_RFIF,#0x00
                           1458 ;	radio.c:111: cons_putsln("Done TX");
   027E 90 0E 39           1459 	mov	dptr,#__str_2
   0281 75 F0 80           1460 	mov	b,#0x80
   0284 02 00 EF           1461 	ljmp	_cons_putsln
                           1462 ;------------------------------------------------------------
                           1463 ;Allocation info for local variables in function 'sendllap'
                           1464 ;------------------------------------------------------------
                           1465 ;count                     Allocated with name '_sendllap_PARM_2'
                           1466 ;m                         Allocated to registers r2 r3 r4 
                           1467 ;i                         Allocated to registers r2 r3 
                           1468 ;------------------------------------------------------------
                           1469 ;	radio.c:114: void sendllap(char *m, int count) {
                           1470 ;	-----------------------------------------
                           1471 ;	 function sendllap
                           1472 ;	-----------------------------------------
   0287                    1473 _sendllap:
   0287 AA 82              1474 	mov	r2,dpl
   0289 AB 83              1475 	mov	r3,dph
   028B AC F0              1476 	mov	r4,b
                           1477 ;	radio.c:125: sprintf(packet, "%s%s%s%s", preamble, "a", llapid, m);
   028D C0 02              1478 	push	ar2
   028F C0 03              1479 	push	ar3
   0291 C0 04              1480 	push	ar4
   0293 74 28              1481 	mov	a,#_llapid
   0295 C0 E0              1482 	push	acc
   0297 74 00              1483 	mov	a,#(_llapid >> 8)
   0299 C0 E0              1484 	push	acc
   029B 74 40              1485 	mov	a,#0x40
   029D C0 E0              1486 	push	acc
   029F 74 4A              1487 	mov	a,#__str_4
   02A1 C0 E0              1488 	push	acc
   02A3 74 0E              1489 	mov	a,#(__str_4 >> 8)
   02A5 C0 E0              1490 	push	acc
   02A7 74 80              1491 	mov	a,#0x80
   02A9 C0 E0              1492 	push	acc
   02AB 74 23              1493 	mov	a,#_preamble
   02AD C0 E0              1494 	push	acc
   02AF 74 00              1495 	mov	a,#(_preamble >> 8)
   02B1 C0 E0              1496 	push	acc
   02B3 74 40              1497 	mov	a,#0x40
   02B5 C0 E0              1498 	push	acc
   02B7 74 41              1499 	mov	a,#__str_3
   02B9 C0 E0              1500 	push	acc
   02BB 74 0E              1501 	mov	a,#(__str_3 >> 8)
   02BD C0 E0              1502 	push	acc
   02BF 74 80              1503 	mov	a,#0x80
   02C1 C0 E0              1504 	push	acc
   02C3 74 00              1505 	mov	a,#_packet
   02C5 C0 E0              1506 	push	acc
   02C7 74 F0              1507 	mov	a,#(_packet >> 8)
   02C9 C0 E0              1508 	push	acc
   02CB E4                 1509 	clr	a
   02CC C0 E0              1510 	push	acc
   02CE 12 07 EA           1511 	lcall	_sprintf
   02D1 E5 81              1512 	mov	a,sp
   02D3 24 EE              1513 	add	a,#0xee
   02D5 F5 81              1514 	mov	sp,a
                           1515 ;	radio.c:127: for (i=0; i<count; i++)
   02D7 7A 00              1516 	mov	r2,#0x00
   02D9 7B 00              1517 	mov	r3,#0x00
   02DB                    1518 00101$:
   02DB C3                 1519 	clr	c
   02DC EA                 1520 	mov	a,r2
   02DD 95 2B              1521 	subb	a,_sendllap_PARM_2
   02DF EB                 1522 	mov	a,r3
   02E0 64 80              1523 	xrl	a,#0x80
   02E2 85 2C F0           1524 	mov	b,(_sendllap_PARM_2 + 1)
   02E5 63 F0 80           1525 	xrl	b,#0x80
   02E8 95 F0              1526 	subb	a,b
   02EA 50 12              1527 	jnc	00105$
                           1528 ;	radio.c:128: sendpacket();
   02EC C0 02              1529 	push	ar2
   02EE C0 03              1530 	push	ar3
   02F0 12 02 51           1531 	lcall	_sendpacket
   02F3 D0 03              1532 	pop	ar3
   02F5 D0 02              1533 	pop	ar2
                           1534 ;	radio.c:127: for (i=0; i<count; i++)
   02F7 0A                 1535 	inc	r2
   02F8 BA 00 E0           1536 	cjne	r2,#0x00,00101$
   02FB 0B                 1537 	inc	r3
   02FC 80 DD              1538 	sjmp	00101$
   02FE                    1539 00105$:
   02FE 22                 1540 	ret
                           1541 ;------------------------------------------------------------
                           1542 ;Allocation info for local variables in function 'getpacket'
                           1543 ;------------------------------------------------------------
                           1544 ;llapmsg                   Allocated with name '_getpacket_llapmsg_1_1'
                           1545 ;n                         Allocated to registers r2 r3 
                           1546 ;------------------------------------------------------------
                           1547 ;	radio.c:131: void getpacket() {
                           1548 ;	-----------------------------------------
                           1549 ;	 function getpacket
                           1550 ;	-----------------------------------------
   02FF                    1551 _getpacket:
                           1552 ;	radio.c:133: if (RFIF & RFIF_IRQ_DONE) {
   02FF E5 E9              1553 	mov	a,_RFIF
   0301 20 E4 03           1554 	jb	acc.4,00150$
   0304 02 05 1B           1555 	ljmp	00127$
   0307                    1556 00150$:
                           1557 ;	radio.c:136: RFIF = 0;
   0307 75 E9 00           1558 	mov	_RFIF,#0x00
                           1559 ;	radio.c:143: cons_putsln("New Packet:");
   030A 90 0E 4C           1560 	mov	dptr,#__str_5
   030D 75 F0 80           1561 	mov	b,#0x80
   0310 12 00 EF           1562 	lcall	_cons_putsln
                           1563 ;	radio.c:145: cons_puthex8(packet[0]);
   0313 90 F0 00           1564 	mov	dptr,#_packet
   0316 E0                 1565 	movx	a,@dptr
   0317 F5 82              1566 	mov	dpl,a
   0319 12 00 FB           1567 	lcall	_cons_puthex8
                           1568 ;	radio.c:146: cons_putsln("");
   031C 90 0E 58           1569 	mov	dptr,#__str_6
   031F 75 F0 80           1570 	mov	b,#0x80
   0322 12 00 EF           1571 	lcall	_cons_putsln
                           1572 ;	radio.c:148: cons_puthex8(packet[1]);
   0325 90 F0 01           1573 	mov	dptr,#(_packet + 0x0001)
   0328 E0                 1574 	movx	a,@dptr
   0329 F5 82              1575 	mov	dpl,a
   032B 12 00 FB           1576 	lcall	_cons_puthex8
                           1577 ;	radio.c:149: cons_puthex8(packet[2]);
   032E 90 F0 02           1578 	mov	dptr,#(_packet + 0x0002)
   0331 E0                 1579 	movx	a,@dptr
   0332 F5 82              1580 	mov	dpl,a
   0334 12 00 FB           1581 	lcall	_cons_puthex8
                           1582 ;	radio.c:150: cons_putsln("");
   0337 90 0E 58           1583 	mov	dptr,#__str_6
   033A 75 F0 80           1584 	mov	b,#0x80
   033D 12 00 EF           1585 	lcall	_cons_putsln
                           1586 ;	radio.c:154: while(n < (packet[0]+1)) {
   0340 7A 03              1587 	mov	r2,#0x03
   0342 7B 00              1588 	mov	r3,#0x00
   0344                    1589 00101$:
   0344 90 F0 00           1590 	mov	dptr,#_packet
   0347 E0                 1591 	movx	a,@dptr
   0348 FC                 1592 	mov	r4,a
   0349 7D 00              1593 	mov	r5,#0x00
   034B 0C                 1594 	inc	r4
   034C BC 00 01           1595 	cjne	r4,#0x00,00151$
   034F 0D                 1596 	inc	r5
   0350                    1597 00151$:
   0350 C3                 1598 	clr	c
   0351 EA                 1599 	mov	a,r2
   0352 9C                 1600 	subb	a,r4
   0353 EB                 1601 	mov	a,r3
   0354 9D                 1602 	subb	a,r5
   0355 50 35              1603 	jnc	00103$
                           1604 ;	radio.c:155: llapmsg[n-3] = packet[n];
   0357 8A 04              1605 	mov	ar4,r2
   0359 EC                 1606 	mov	a,r4
   035A 24 2A              1607 	add	a,#0xfd+_getpacket_llapmsg_1_1
   035C F8                 1608 	mov	r0,a
   035D EA                 1609 	mov	a,r2
   035E 24 00              1610 	add	a,#_packet
   0360 F5 82              1611 	mov	dpl,a
   0362 EB                 1612 	mov	a,r3
   0363 34 F0              1613 	addc	a,#(_packet >> 8)
   0365 F5 83              1614 	mov	dph,a
   0367 E0                 1615 	movx	a,@dptr
   0368 F6                 1616 	mov	@r0,a
                           1617 ;	radio.c:156: cons_putc(packet[n++]);
   0369 8A 04              1618 	mov	ar4,r2
   036B 8B 05              1619 	mov	ar5,r3
   036D 0A                 1620 	inc	r2
   036E BA 00 01           1621 	cjne	r2,#0x00,00153$
   0371 0B                 1622 	inc	r3
   0372                    1623 00153$:
   0372 EC                 1624 	mov	a,r4
   0373 24 00              1625 	add	a,#_packet
   0375 F5 82              1626 	mov	dpl,a
   0377 ED                 1627 	mov	a,r5
   0378 34 F0              1628 	addc	a,#(_packet >> 8)
   037A F5 83              1629 	mov	dph,a
   037C E0                 1630 	movx	a,@dptr
   037D F5 82              1631 	mov	dpl,a
   037F C0 02              1632 	push	ar2
   0381 C0 03              1633 	push	ar3
   0383 12 00 B8           1634 	lcall	_cons_putc
   0386 D0 03              1635 	pop	ar3
   0388 D0 02              1636 	pop	ar2
   038A 80 B8              1637 	sjmp	00101$
   038C                    1638 00103$:
                           1639 ;	radio.c:158: llapmsg[12] = '\0';
   038C 75 39 00           1640 	mov	(_getpacket_llapmsg_1_1 + 0x000c),#0x00
                           1641 ;	radio.c:160: cons_putsln("");
   038F 90 0E 58           1642 	mov	dptr,#__str_6
   0392 75 F0 80           1643 	mov	b,#0x80
   0395 12 00 EF           1644 	lcall	_cons_putsln
                           1645 ;	radio.c:161: cons_puts("RSSI: ");
   0398 90 0E 59           1646 	mov	dptr,#__str_7
   039B 75 F0 80           1647 	mov	b,#0x80
   039E 12 00 C4           1648 	lcall	_cons_puts
                           1649 ;	radio.c:162: cons_puthex8(RSSI);
   03A1 90 DF 3A           1650 	mov	dptr,#_RSSI
   03A4 E0                 1651 	movx	a,@dptr
   03A5 F5 82              1652 	mov	dpl,a
   03A7 12 00 FB           1653 	lcall	_cons_puthex8
                           1654 ;	radio.c:164: cons_puts(" LQI: ");
   03AA 90 0E 60           1655 	mov	dptr,#__str_8
   03AD 75 F0 80           1656 	mov	b,#0x80
   03B0 12 00 C4           1657 	lcall	_cons_puts
                           1658 ;	radio.c:165: cons_puthex8(LQI);
   03B3 90 DF 39           1659 	mov	dptr,#_LQI
   03B6 E0                 1660 	movx	a,@dptr
   03B7 F5 82              1661 	mov	dpl,a
   03B9 12 00 FB           1662 	lcall	_cons_puthex8
                           1663 ;	radio.c:166: cons_putsln("");
   03BC 90 0E 58           1664 	mov	dptr,#__str_6
   03BF 75 F0 80           1665 	mov	b,#0x80
   03C2 12 00 EF           1666 	lcall	_cons_putsln
                           1667 ;	radio.c:168: if (PKTSTATUS & 0x80) {
   03C5 90 DF 3C           1668 	mov	dptr,#_PKTSTATUS
   03C8 E0                 1669 	movx	a,@dptr
   03C9 FA                 1670 	mov	r2,a
   03CA 30 E7 0B           1671 	jnb	acc.7,00105$
                           1672 ;	radio.c:169: cons_putsln("CRC: OK");
   03CD 90 0E 67           1673 	mov	dptr,#__str_9
   03D0 75 F0 80           1674 	mov	b,#0x80
   03D3 12 00 EF           1675 	lcall	_cons_putsln
   03D6 80 09              1676 	sjmp	00106$
   03D8                    1677 00105$:
                           1678 ;	radio.c:172: cons_putsln("CRC: Fail");
   03D8 90 0E 6F           1679 	mov	dptr,#__str_10
   03DB 75 F0 80           1680 	mov	b,#0x80
   03DE 12 00 EF           1681 	lcall	_cons_putsln
   03E1                    1682 00106$:
                           1683 ;	radio.c:176: if (strncmp(llapmsg, "aLL", 3) == 0) {
   03E1 75 10 79           1684 	mov	_strncmp_PARM_2,#__str_11
   03E4 75 11 0E           1685 	mov	(_strncmp_PARM_2 + 1),#(__str_11 >> 8)
   03E7 75 12 80           1686 	mov	(_strncmp_PARM_2 + 2),#0x80
   03EA 75 13 03           1687 	mov	_strncmp_PARM_3,#0x03
   03ED E4                 1688 	clr	a
   03EE F5 14              1689 	mov	(_strncmp_PARM_3 + 1),a
   03F0 90 00 2D           1690 	mov	dptr,#_getpacket_llapmsg_1_1
   03F3 75 F0 40           1691 	mov	b,#0x40
   03F6 12 06 93           1692 	lcall	_strncmp
   03F9 E5 82              1693 	mov	a,dpl
   03FB 85 83 F0           1694 	mov	b,dph
   03FE 45 F0              1695 	orl	a,b
   0400 60 03              1696 	jz	00155$
   0402 02 05 1B           1697 	ljmp	00127$
   0405                    1698 00155$:
                           1699 ;	radio.c:178: if (strncmp(llapmsg+3, "LEDON----", 9) == 0) {
   0405 75 10 7D           1700 	mov	_strncmp_PARM_2,#__str_12
   0408 75 11 0E           1701 	mov	(_strncmp_PARM_2 + 1),#(__str_12 >> 8)
   040B 75 12 80           1702 	mov	(_strncmp_PARM_2 + 2),#0x80
   040E 75 13 09           1703 	mov	_strncmp_PARM_3,#0x09
   0411 E4                 1704 	clr	a
   0412 F5 14              1705 	mov	(_strncmp_PARM_3 + 1),a
   0414 90 00 30           1706 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   0417 75 F0 40           1707 	mov	b,#0x40
   041A 12 06 93           1708 	lcall	_strncmp
   041D E5 82              1709 	mov	a,dpl
   041F 85 83 F0           1710 	mov	b,dph
   0422 45 F0              1711 	orl	a,b
   0424 70 14              1712 	jnz	00122$
                           1713 ;	radio.c:179: sendllap(llapmsg, 1);
   0426 75 2B 01           1714 	mov	_sendllap_PARM_2,#0x01
   0429 E4                 1715 	clr	a
   042A F5 2C              1716 	mov	(_sendllap_PARM_2 + 1),a
   042C 90 00 2D           1717 	mov	dptr,#_getpacket_llapmsg_1_1
   042F 75 F0 40           1718 	mov	b,#0x40
   0432 12 02 87           1719 	lcall	_sendllap
                           1720 ;	radio.c:180: P1_3 = 1; // turn on
   0435 D2 93              1721 	setb	_P1_3
   0437 02 05 1B           1722 	ljmp	00127$
   043A                    1723 00122$:
                           1724 ;	radio.c:181: } else if (strncmp(llapmsg+3, "LEDOFF---", 9) == 0) {
   043A 75 10 87           1725 	mov	_strncmp_PARM_2,#__str_13
   043D 75 11 0E           1726 	mov	(_strncmp_PARM_2 + 1),#(__str_13 >> 8)
   0440 75 12 80           1727 	mov	(_strncmp_PARM_2 + 2),#0x80
   0443 75 13 09           1728 	mov	_strncmp_PARM_3,#0x09
   0446 E4                 1729 	clr	a
   0447 F5 14              1730 	mov	(_strncmp_PARM_3 + 1),a
   0449 90 00 30           1731 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   044C 75 F0 40           1732 	mov	b,#0x40
   044F 12 06 93           1733 	lcall	_strncmp
   0452 E5 82              1734 	mov	a,dpl
   0454 85 83 F0           1735 	mov	b,dph
   0457 45 F0              1736 	orl	a,b
   0459 70 14              1737 	jnz	00119$
                           1738 ;	radio.c:182: sendllap(llapmsg, 1);
   045B 75 2B 01           1739 	mov	_sendllap_PARM_2,#0x01
   045E E4                 1740 	clr	a
   045F F5 2C              1741 	mov	(_sendllap_PARM_2 + 1),a
   0461 90 00 2D           1742 	mov	dptr,#_getpacket_llapmsg_1_1
   0464 75 F0 40           1743 	mov	b,#0x40
   0467 12 02 87           1744 	lcall	_sendllap
                           1745 ;	radio.c:183: P1_3 = 0; // turn off
   046A C2 93              1746 	clr	_P1_3
   046C 02 05 1B           1747 	ljmp	00127$
   046F                    1748 00119$:
                           1749 ;	radio.c:184: } else if (strncmp(llapmsg+3, "HELLO----", 9) == 0) {
   046F 75 10 91           1750 	mov	_strncmp_PARM_2,#__str_14
   0472 75 11 0E           1751 	mov	(_strncmp_PARM_2 + 1),#(__str_14 >> 8)
   0475 75 12 80           1752 	mov	(_strncmp_PARM_2 + 2),#0x80
   0478 75 13 09           1753 	mov	_strncmp_PARM_3,#0x09
   047B E4                 1754 	clr	a
   047C F5 14              1755 	mov	(_strncmp_PARM_3 + 1),a
   047E 90 00 30           1756 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   0481 75 F0 40           1757 	mov	b,#0x40
   0484 12 06 93           1758 	lcall	_strncmp
   0487 E5 82              1759 	mov	a,dpl
   0489 85 83 F0           1760 	mov	b,dph
   048C 45 F0              1761 	orl	a,b
   048E 70 12              1762 	jnz	00116$
                           1763 ;	radio.c:186: sendllap(llapmsg, 1);
   0490 75 2B 01           1764 	mov	_sendllap_PARM_2,#0x01
   0493 E4                 1765 	clr	a
   0494 F5 2C              1766 	mov	(_sendllap_PARM_2 + 1),a
   0496 90 00 2D           1767 	mov	dptr,#_getpacket_llapmsg_1_1
   0499 75 F0 40           1768 	mov	b,#0x40
   049C 12 02 87           1769 	lcall	_sendllap
   049F 02 05 1B           1770 	ljmp	00127$
   04A2                    1771 00116$:
                           1772 ;	radio.c:187: } else if (strncmp(llapmsg+3, "REBOOT---", 9) == 0) {
   04A2 75 10 9B           1773 	mov	_strncmp_PARM_2,#__str_15
   04A5 75 11 0E           1774 	mov	(_strncmp_PARM_2 + 1),#(__str_15 >> 8)
   04A8 75 12 80           1775 	mov	(_strncmp_PARM_2 + 2),#0x80
   04AB 75 13 09           1776 	mov	_strncmp_PARM_3,#0x09
   04AE E4                 1777 	clr	a
   04AF F5 14              1778 	mov	(_strncmp_PARM_3 + 1),a
   04B1 90 00 30           1779 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   04B4 75 F0 40           1780 	mov	b,#0x40
   04B7 12 06 93           1781 	lcall	_strncmp
   04BA E5 82              1782 	mov	a,dpl
   04BC 85 83 F0           1783 	mov	b,dph
   04BF 45 F0              1784 	orl	a,b
   04C1 70 14              1785 	jnz	00113$
                           1786 ;	radio.c:189: sendllap(llapmsg, 1);
   04C3 75 2B 01           1787 	mov	_sendllap_PARM_2,#0x01
   04C6 E4                 1788 	clr	a
   04C7 F5 2C              1789 	mov	(_sendllap_PARM_2 + 1),a
   04C9 90 00 2D           1790 	mov	dptr,#_getpacket_llapmsg_1_1
   04CC 75 F0 40           1791 	mov	b,#0x40
   04CF 12 02 87           1792 	lcall	_sendllap
                           1793 ;	radio.c:190: __asm LCALL 0x0 __endasm;
   04D2 12 00 00           1794 	 LCALL 0x0 
   04D5 80 44              1795 	sjmp	00127$
   04D7                    1796 00113$:
                           1797 ;	radio.c:191: } else if (strncmp(llapmsg+3, "LED------", 9) == 0) {
   04D7 75 10 A5           1798 	mov	_strncmp_PARM_2,#__str_16
   04DA 75 11 0E           1799 	mov	(_strncmp_PARM_2 + 1),#(__str_16 >> 8)
   04DD 75 12 80           1800 	mov	(_strncmp_PARM_2 + 2),#0x80
   04E0 75 13 09           1801 	mov	_strncmp_PARM_3,#0x09
   04E3 E4                 1802 	clr	a
   04E4 F5 14              1803 	mov	(_strncmp_PARM_3 + 1),a
   04E6 90 00 30           1804 	mov	dptr,#(_getpacket_llapmsg_1_1 + 0x0003)
   04E9 75 F0 40           1805 	mov	b,#0x40
   04EC 12 06 93           1806 	lcall	_strncmp
   04EF E5 82              1807 	mov	a,dpl
   04F1 85 83 F0           1808 	mov	b,dph
   04F4 45 F0              1809 	orl	a,b
   04F6 70 23              1810 	jnz	00127$
                           1811 ;	radio.c:193: if (P1_3 == 0) {
   04F8 20 93 11           1812 	jb	_P1_3,00108$
                           1813 ;	radio.c:194: sendllap("LEDOFF---", 1);
   04FB 75 2B 01           1814 	mov	_sendllap_PARM_2,#0x01
   04FE E4                 1815 	clr	a
   04FF F5 2C              1816 	mov	(_sendllap_PARM_2 + 1),a
   0501 90 0E 87           1817 	mov	dptr,#__str_13
   0504 75 F0 80           1818 	mov	b,#0x80
   0507 12 02 87           1819 	lcall	_sendllap
   050A 80 0F              1820 	sjmp	00127$
   050C                    1821 00108$:
                           1822 ;	radio.c:196: sendllap("LEDON----", 1);
   050C 75 2B 01           1823 	mov	_sendllap_PARM_2,#0x01
   050F E4                 1824 	clr	a
   0510 F5 2C              1825 	mov	(_sendllap_PARM_2 + 1),a
   0512 90 0E 7D           1826 	mov	dptr,#__str_12
   0515 75 F0 80           1827 	mov	b,#0x80
   0518 12 02 87           1828 	lcall	_sendllap
   051B                    1829 00127$:
                           1830 ;	radio.c:201: if (MARCSTATE != MARC_STATE_RX) {
   051B 90 DF 3B           1831 	mov	dptr,#_MARCSTATE
   051E E0                 1832 	movx	a,@dptr
   051F FA                 1833 	mov	r2,a
   0520 BA 0D 01           1834 	cjne	r2,#0x0D,00162$
   0523 22                 1835 	ret
   0524                    1836 00162$:
                           1837 ;	radio.c:202: packet_index = 0;
   0524 75 22 00           1838 	mov	_packet_index,#0x00
                           1839 ;	radio.c:203: RFST = RFST_SRX;
   0527 75 E1 02           1840 	mov	_RFST,#0x02
                           1841 ;	radio.c:204: while (MARCSTATE != MARC_STATE_RX);
   052A                    1842 00128$:
   052A 90 DF 3B           1843 	mov	dptr,#_MARCSTATE
   052D E0                 1844 	movx	a,@dptr
   052E FA                 1845 	mov	r2,a
   052F BA 0D F8           1846 	cjne	r2,#0x0D,00128$
                           1847 ;	radio.c:205: cons_putsln("Waiting to receive...");
   0532 90 0E AF           1848 	mov	dptr,#__str_17
   0535 75 F0 80           1849 	mov	b,#0x80
   0538 02 00 EF           1850 	ljmp	_cons_putsln
                           1851 ;------------------------------------------------------------
                           1852 ;Allocation info for local variables in function 'radio_init'
                           1853 ;------------------------------------------------------------
                           1854 ;------------------------------------------------------------
                           1855 ;	radio.c:209: void radio_init(void) {
                           1856 ;	-----------------------------------------
                           1857 ;	 function radio_init
                           1858 ;	-----------------------------------------
   053B                    1859 _radio_init:
                           1860 ;	radio.c:212: SLEEP &= ~SLEEP_OSC_PD;
   053B 53 BE FB           1861 	anl	_SLEEP,#0xFB
                           1862 ;	radio.c:214: while( !(SLEEP & SLEEP_XOSC_S) ); 
   053E                    1863 00101$:
   053E E5 BE              1864 	mov	a,_SLEEP
   0540 30 E6 FB           1865 	jnb	acc.6,00101$
                           1866 ;	radio.c:227: (CLKCON & ~(CLKCON_CLKSPD | CLKCON_OSC))
   0543 AA C6              1867 	mov	r2,_CLKCON
   0545 74 B8              1868 	mov	a,#0xB8
   0547 5A                 1869 	anl	a,r2
   0548 F5 F0              1870 	mov	b,a
   054A 74 01              1871 	mov	a,#0x01
   054C 45 F0              1872 	orl	a,b
   054E F5 C6              1873 	mov	_CLKCON,a
                           1874 ;	radio.c:231: while (CLKCON & CLKCON_OSC); 
   0550                    1875 00104$:
   0550 E5 C6              1876 	mov	a,_CLKCON
   0552 20 E6 FB           1877 	jb	acc.6,00104$
                           1878 ;	radio.c:233: SLEEP |= SLEEP_OSC_PD; 
   0555 43 BE 04           1879 	orl	_SLEEP,#0x04
                           1880 ;	radio.c:236: RFST=RFST_SIDLE; // enter idle state
   0558 75 E1 04           1881 	mov	_RFST,#0x04
                           1882 ;	radio.c:238: FREQ0 = 0x24;
   055B 90 DF 0B           1883 	mov	dptr,#_FREQ0
   055E 74 24              1884 	mov	a,#0x24
   0560 F0                 1885 	movx	@dptr,a
                           1886 ;	radio.c:239: FREQ1 = 0x2D;
   0561 90 DF 0A           1887 	mov	dptr,#_FREQ1
   0564 74 2D              1888 	mov	a,#0x2D
   0566 F0                 1889 	movx	@dptr,a
                           1890 ;	radio.c:240: FREQ2 = 0x24;
   0567 90 DF 09           1891 	mov	dptr,#_FREQ2
   056A 74 24              1892 	mov	a,#0x24
   056C F0                 1893 	movx	@dptr,a
                           1894 ;	radio.c:241: PA_TABLE0 = 0xC2;
   056D 90 DF 2E           1895 	mov	dptr,#_PA_TABLE0
   0570 74 C2              1896 	mov	a,#0xC2
   0572 F0                 1897 	movx	@dptr,a
                           1898 ;	radio.c:242: FSCTRL1 = 0x0C; // FSCTRL1 Frequency Synthesizer Control 
   0573 90 DF 07           1899 	mov	dptr,#_FSCTRL1
   0576 74 0C              1900 	mov	a,#0x0C
   0578 F0                 1901 	movx	@dptr,a
                           1902 ;	radio.c:243: MDMCFG4 = 0x1D; // MDMCFG4 Modem configuration 
   0579 90 DF 0C           1903 	mov	dptr,#_MDMCFG4
   057C 74 1D              1904 	mov	a,#0x1D
   057E F0                 1905 	movx	@dptr,a
                           1906 ;	radio.c:244: MDMCFG3 = 0x55; // MDMCFG3 Modem Configuration 
   057F 90 DF 0D           1907 	mov	dptr,#_MDMCFG3
   0582 74 55              1908 	mov	a,#0x55
   0584 F0                 1909 	movx	@dptr,a
                           1910 ;	radio.c:245: MDMCFG2 = 0x13; // MDMCFG2 Modem Configuration 
   0585 90 DF 0E           1911 	mov	dptr,#_MDMCFG2
   0588 74 13              1912 	mov	a,#0x13
   058A F0                 1913 	movx	@dptr,a
                           1914 ;	radio.c:246: DEVIATN = 0x63; // DEVIATN Modem Deviation Setting 
   058B 90 DF 11           1915 	mov	dptr,#_DEVIATN
   058E 74 63              1916 	mov	a,#0x63
   0590 F0                 1917 	movx	@dptr,a
                           1918 ;	radio.c:247: FREND1 = 0xB6; // FREND1 Front End RX Configuration 
   0591 90 DF 1A           1919 	mov	dptr,#_FREND1
   0594 74 B6              1920 	mov	a,#0xB6
   0596 F0                 1921 	movx	@dptr,a
                           1922 ;	radio.c:248: FOCCFG = 0x1D; // FOCCFG Frequency Offset Compensation Configuration 
   0597 90 DF 15           1923 	mov	dptr,#_FOCCFG
   059A 74 1D              1924 	mov	a,#0x1D
   059C F0                 1925 	movx	@dptr,a
                           1926 ;	radio.c:249: BSCFG = 0x1C; // BSCFG Bit Synchronization Configuration 
   059D 90 DF 16           1927 	mov	dptr,#_BSCFG
   05A0 74 1C              1928 	mov	a,#0x1C
   05A2 F0                 1929 	movx	@dptr,a
                           1930 ;	radio.c:250: AGCCTRL2 = 0xC7; // AGCCTRL2 AGC Control 
   05A3 90 DF 17           1931 	mov	dptr,#_AGCCTRL2
   05A6 74 C7              1932 	mov	a,#0xC7
   05A8 F0                 1933 	movx	@dptr,a
                           1934 ;	radio.c:251: AGCCTRL1 = 0x00; // AGCCTRL1 AGC Control 
   05A9 90 DF 18           1935 	mov	dptr,#_AGCCTRL1
   05AC E4                 1936 	clr	a
   05AD F0                 1937 	movx	@dptr,a
                           1938 ;	radio.c:252: AGCCTRL0 = 0xB0; // AGCCTRL0 AGC Control 
   05AE 90 DF 19           1939 	mov	dptr,#_AGCCTRL0
   05B1 74 B0              1940 	mov	a,#0xB0
   05B3 F0                 1941 	movx	@dptr,a
                           1942 ;	radio.c:253: FSCAL3 = 0xEA; // FSCAL3 Frequency Synthesizer Calibration 
   05B4 90 DF 1C           1943 	mov	dptr,#_FSCAL3
   05B7 74 EA              1944 	mov	a,#0xEA
   05B9 F0                 1945 	movx	@dptr,a
                           1946 ;	radio.c:254: FSCTRL0 = 0x00; // Frequency synthesizer control.
   05BA 90 DF 08           1947 	mov	dptr,#_FSCTRL0
   05BD E4                 1948 	clr	a
   05BE F0                 1949 	movx	@dptr,a
                           1950 ;	radio.c:255: FREND0 = 0x10; // Front end TX configuration.
   05BF 90 DF 1B           1951 	mov	dptr,#_FREND0
   05C2 74 10              1952 	mov	a,#0x10
   05C4 F0                 1953 	movx	@dptr,a
                           1954 ;	radio.c:256: MCSM0 = 0x18; // Main Radio Control State Machine configuration.
   05C5 90 DF 14           1955 	mov	dptr,#_MCSM0
   05C8 74 18              1956 	mov	a,#0x18
   05CA F0                 1957 	movx	@dptr,a
                           1958 ;	radio.c:257: FSCAL3 = 0xEA;
   05CB 90 DF 1C           1959 	mov	dptr,#_FSCAL3
   05CE 74 EA              1960 	mov	a,#0xEA
   05D0 F0                 1961 	movx	@dptr,a
                           1962 ;	radio.c:258: FSCAL2 = 0x2A;
   05D1 90 DF 1D           1963 	mov	dptr,#_FSCAL2
   05D4 74 2A              1964 	mov	a,#0x2A
   05D6 F0                 1965 	movx	@dptr,a
                           1966 ;	radio.c:259: FSCAL1 = 0x00; // Frequency synthesizer calibration.
   05D7 90 DF 1E           1967 	mov	dptr,#_FSCAL1
   05DA E4                 1968 	clr	a
   05DB F0                 1969 	movx	@dptr,a
                           1970 ;	radio.c:260: FSCAL0 = 0x1F; // Frequency synthesizer calibration.
   05DC 90 DF 1F           1971 	mov	dptr,#_FSCAL0
   05DF 74 1F              1972 	mov	a,#0x1F
   05E1 F0                 1973 	movx	@dptr,a
                           1974 ;	radio.c:261: TEST2 = 0x88; // Various test settings.
   05E2 90 DF 23           1975 	mov	dptr,#_TEST2
   05E5 74 88              1976 	mov	a,#0x88
   05E7 F0                 1977 	movx	@dptr,a
                           1978 ;	radio.c:262: TEST1 = 0x31; // Various test settings.
   05E8 90 DF 24           1979 	mov	dptr,#_TEST1
   05EB 74 31              1980 	mov	a,#0x31
   05ED F0                 1981 	movx	@dptr,a
                           1982 ;	radio.c:263: TEST0 = 0x09; // Various test settings.
   05EE 90 DF 25           1983 	mov	dptr,#_TEST0
   05F1 74 09              1984 	mov	a,#0x09
   05F3 F0                 1985 	movx	@dptr,a
                           1986 ;	radio.c:266: MDMCFG1 = 0x23; // calc for 24 MHz
   05F4 90 DF 0F           1987 	mov	dptr,#_MDMCFG1
   05F7 74 23              1988 	mov	a,#0x23
   05F9 F0                 1989 	movx	@dptr,a
                           1990 ;	radio.c:267: MDMCFG0 = 0x11; // calc for 24 MHz
   05FA 90 DF 10           1991 	mov	dptr,#_MDMCFG0
   05FD 74 11              1992 	mov	a,#0x11
   05FF F0                 1993 	movx	@dptr,a
                           1994 ;	radio.c:268: CHANNR = 0x00;
   0600 90 DF 06           1995 	mov	dptr,#_CHANNR
   0603 E4                 1996 	clr	a
   0604 F0                 1997 	movx	@dptr,a
                           1998 ;	radio.c:269: MCSM1 = 0x30; // Main Radio Control State Machine configuration.
   0605 90 DF 13           1999 	mov	dptr,#_MCSM1
   0608 74 30              2000 	mov	a,#0x30
   060A F0                 2001 	movx	@dptr,a
                           2002 ;	radio.c:270: PKTCTRL1 = 0x04; // Packet automation control.
   060B 90 DF 03           2003 	mov	dptr,#_PKTCTRL1
   060E 74 04              2004 	mov	a,#0x04
   0610 F0                 2005 	movx	@dptr,a
                           2006 ;	radio.c:271: PKTCTRL0 = 0x45; // Packet automation control. Data whitening on.
   0611 90 DF 04           2007 	mov	dptr,#_PKTCTRL0
   0614 74 45              2008 	mov	a,#0x45
   0616 F0                 2009 	movx	@dptr,a
                           2010 ;	radio.c:272: ADDR = 0x00; // Device address. Not used.
   0617 90 DF 05           2011 	mov	dptr,#_ADDR
   061A E4                 2012 	clr	a
   061B F0                 2013 	movx	@dptr,a
                           2014 ;	radio.c:273: PKTLEN = 0x0F;
   061C 90 DF 02           2015 	mov	dptr,#_PKTLEN
   061F 74 0F              2016 	mov	a,#0x0F
   0621 F0                 2017 	movx	@dptr,a
                           2018 ;	radio.c:274: rssi_offset = 77;
   0622 75 26 4D           2019 	mov	_rssi_offset,#0x4D
   0625 E4                 2020 	clr	a
   0626 F5 27              2021 	mov	(_rssi_offset + 1),a
                           2022 ;	radio.c:275: RFIF = 0;
   0628 75 E9 00           2023 	mov	_RFIF,#0x00
                           2024 ;	radio.c:276: packet_index = 0;
   062B 75 22 00           2025 	mov	_packet_index,#0x00
                           2026 ;	radio.c:278: RFTXRXIF=0;
   062E C2 89              2027 	clr	_RFTXRXIF
                           2028 ;	radio.c:279: RFTXRXIE=1;
   0630 D2 A8              2029 	setb	_RFTXRXIE
                           2030 ;	radio.c:282: RFST=RFST_SIDLE;
   0632 75 E1 04           2031 	mov	_RFST,#0x04
                           2032 ;	radio.c:283: while(MARCSTATE!=MARC_STATE_IDLE);
   0635                    2033 00107$:
   0635 90 DF 3B           2034 	mov	dptr,#_MARCSTATE
   0638 E0                 2035 	movx	a,@dptr
   0639 FA                 2036 	mov	r2,a
   063A BA 01 F8           2037 	cjne	r2,#0x01,00107$
                           2038 ;	radio.c:284: cons_putsln("Radio Started");
   063D 90 0E C5           2039 	mov	dptr,#__str_18
   0640 75 F0 80           2040 	mov	b,#0x80
   0643 02 00 EF           2041 	ljmp	_cons_putsln
                           2042 ;------------------------------------------------------------
                           2043 ;Allocation info for local variables in function 'main'
                           2044 ;------------------------------------------------------------
                           2045 ;swstate                   Allocated with name '_main_swstate_1_1'
                           2046 ;------------------------------------------------------------
                           2047 ;	radio.c:287: void main() {
                           2048 ;	-----------------------------------------
                           2049 ;	 function main
                           2050 ;	-----------------------------------------
   0646                    2051 _main:
                           2052 ;	radio.c:292: PERCFG = (PERCFG & ~PERCFG_U0CFG) | PERCFG_U1CFG;
   0646 AA F1              2053 	mov	r2,_PERCFG
   0648 74 FE              2054 	mov	a,#0xFE
   064A 5A                 2055 	anl	a,r2
   064B F5 F0              2056 	mov	b,a
   064D 74 02              2057 	mov	a,#0x02
   064F 45 F0              2058 	orl	a,b
   0651 F5 F1              2059 	mov	_PERCFG,a
                           2060 ;	radio.c:293: P0SEL |= 0x08 | 0x04;
   0653 43 F3 0C           2061 	orl	_P0SEL,#0x0C
                           2062 ;	radio.c:294: U0CSR |= 0x80 | 0x40;
   0656 43 86 C0           2063 	orl	_U0CSR,#0xC0
                           2064 ;	radio.c:296: U0GCR = 13;
   0659 75 C5 0D           2065 	mov	_U0GCR,#0x0D
                           2066 ;	radio.c:297: U0BAUD = 59;
   065C 75 C2 3B           2067 	mov	_U0BAUD,#0x3B
                           2068 ;	radio.c:298: URX0IF = 0;
   065F C2 8B              2069 	clr	_URX0IF
                           2070 ;	radio.c:301: P1DIR |= 0x08;
   0661 43 FE 08           2071 	orl	_P1DIR,#0x08
                           2072 ;	radio.c:302: P1_3 = 0;
   0664 C2 93              2073 	clr	_P1_3
                           2074 ;	radio.c:305: swstate = P1_6;
   0666 A2 96              2075 	mov	c,_P1_6
   0668 E4                 2076 	clr	a
   0669 33                 2077 	rlc	a
   066A F5 3A              2078 	mov	_main_swstate_1_1,a
   066C 75 3B 00           2079 	mov	(_main_swstate_1_1 + 1),#0x00
                           2080 ;	radio.c:307: radio_init();
   066F 12 05 3B           2081 	lcall	_radio_init
                           2082 ;	radio.c:310: F1 = 1;
   0672 D2 D1              2083 	setb	_F1
                           2084 ;	radio.c:311: EA = 1;
   0674 D2 AF              2085 	setb	_EA
                           2086 ;	radio.c:314: sendllap("STARTING-", 5);
   0676 75 2B 05           2087 	mov	_sendllap_PARM_2,#0x05
   0679 E4                 2088 	clr	a
   067A F5 2C              2089 	mov	(_sendllap_PARM_2 + 1),a
   067C 90 0E D3           2090 	mov	dptr,#__str_19
   067F 75 F0 80           2091 	mov	b,#0x80
   0682 12 02 87           2092 	lcall	_sendllap
                           2093 ;	radio.c:316: while(1) {
   0685                    2094 00102$:
                           2095 ;	radio.c:318: getpacket();
   0685 12 02 FF           2096 	lcall	_getpacket
                           2097 ;	radio.c:320: switchchange(&swstate);
   0688 90 00 3A           2098 	mov	dptr,#_main_swstate_1_1
   068B 75 F0 40           2099 	mov	b,#0x40
   068E 12 01 BD           2100 	lcall	_switchchange
   0691 80 F2              2101 	sjmp	00102$
                           2102 	.area CSEG    (CODE)
                           2103 	.area CONST   (CODE)
   0E2D                    2104 __str_0:
   0E2D 0D                 2105 	.db 0x0D
   0E2E 0A                 2106 	.db 0x0A
   0E2F 00                 2107 	.db 0x00
   0E30                    2108 __str_1:
   0E30 53 74 61 72 74 20  2109 	.ascii "Start TX"
        54 58
   0E38 00                 2110 	.db 0x00
   0E39                    2111 __str_2:
   0E39 44 6F 6E 65 20 54  2112 	.ascii "Done TX"
        58
   0E40 00                 2113 	.db 0x00
   0E41                    2114 __str_3:
   0E41 25 73 25 73 25 73  2115 	.ascii "%s%s%s%s"
        25 73
   0E49 00                 2116 	.db 0x00
   0E4A                    2117 __str_4:
   0E4A 61                 2118 	.ascii "a"
   0E4B 00                 2119 	.db 0x00
   0E4C                    2120 __str_5:
   0E4C 4E 65 77 20 50 61  2121 	.ascii "New Packet:"
        63 6B 65 74 3A
   0E57 00                 2122 	.db 0x00
   0E58                    2123 __str_6:
   0E58 00                 2124 	.db 0x00
   0E59                    2125 __str_7:
   0E59 52 53 53 49 3A 20  2126 	.ascii "RSSI: "
   0E5F 00                 2127 	.db 0x00
   0E60                    2128 __str_8:
   0E60 20 4C 51 49 3A 20  2129 	.ascii " LQI: "
   0E66 00                 2130 	.db 0x00
   0E67                    2131 __str_9:
   0E67 43 52 43 3A 20 4F  2132 	.ascii "CRC: OK"
        4B
   0E6E 00                 2133 	.db 0x00
   0E6F                    2134 __str_10:
   0E6F 43 52 43 3A 20 46  2135 	.ascii "CRC: Fail"
        61 69 6C
   0E78 00                 2136 	.db 0x00
   0E79                    2137 __str_11:
   0E79 61 4C 4C           2138 	.ascii "aLL"
   0E7C 00                 2139 	.db 0x00
   0E7D                    2140 __str_12:
   0E7D 4C 45 44 4F 4E 2D  2141 	.ascii "LEDON----"
        2D 2D 2D
   0E86 00                 2142 	.db 0x00
   0E87                    2143 __str_13:
   0E87 4C 45 44 4F 46 46  2144 	.ascii "LEDOFF---"
        2D 2D 2D
   0E90 00                 2145 	.db 0x00
   0E91                    2146 __str_14:
   0E91 48 45 4C 4C 4F 2D  2147 	.ascii "HELLO----"
        2D 2D 2D
   0E9A 00                 2148 	.db 0x00
   0E9B                    2149 __str_15:
   0E9B 52 45 42 4F 4F 54  2150 	.ascii "REBOOT---"
        2D 2D 2D
   0EA4 00                 2151 	.db 0x00
   0EA5                    2152 __str_16:
   0EA5 4C 45 44 2D 2D 2D  2153 	.ascii "LED------"
        2D 2D 2D
   0EAE 00                 2154 	.db 0x00
   0EAF                    2155 __str_17:
   0EAF 57 61 69 74 69 6E  2156 	.ascii "Waiting to receive..."
        67 20 74 6F 20 72
        65 63 65 69 76 65
        2E 2E 2E
   0EC4 00                 2157 	.db 0x00
   0EC5                    2158 __str_18:
   0EC5 52 61 64 69 6F 20  2159 	.ascii "Radio Started"
        53 74 61 72 74 65
        64
   0ED2 00                 2160 	.db 0x00
   0ED3                    2161 __str_19:
   0ED3 53 54 41 52 54 49  2162 	.ascii "STARTING-"
        4E 47 2D
   0EDC 00                 2163 	.db 0x00
                           2164 	.area XINIT   (CODE)
                           2165 	.area CABS    (ABS,CODE)
