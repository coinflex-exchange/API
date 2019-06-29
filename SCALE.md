# Scaling


## Amounts

Asset quantities and totals transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset type. All assets have now been set with a scaling factor of 10000 (i.e. 4 decimal places).

| Asset Type | ID (Hex) | ID (Dec) | Scale Factor |  Atomic Unit |
|:----------:|---------:|---------:|-------------:|-------------:|
|     XBT    |   0xF800 |    63488 |        10000 |     Ƀ 0.0001 |
|     BCH    |   0xF808 |    63496 |        10000 |    ɃC 0.0001 |
|     ETH    |   0xF820 |    63520 |        10000 |     Ξ 0.0001 |
|     USDC   |   0xFF02 |    65282 |        10000 |    $C 0.0001 |
|     USDT   |   0xFF03 |    65283 |        10000 |    $T 0.0001 |
|     FLEX   |   0xFF05 |    65285 |        10000 |    FL 0.0001 |
|  XBTJAN    |   0xC800 |    51200 |        10000 |  JanɃ 0.0001 |
|  BCHJAN    |   0xC814 |    51220 |        10000 | JanɃC 0.0001 |
|  ETHJAN    |   0xC828 |    51240 |        10000 |  JanΞ 0.0001 |
|  USDTJAN   |   0xCAA8 |    51880 |        10000 | Jan$T 0.0001 |
|  USDCJAN   |   0xCA94 |    51860 |        10000 | Jan$C 0.0001 |
|   XBTFEB   |   0xC801 |    51201 |        10000 |  FebɃ 0.0001 |
|   BCHFEB   |   0xC815 |    51221 |        10000 | FebɃC 0.0001 |
|   ETHFEB   |   0xC829 |    51241 |        10000 |  FebΞ 0.0001 |
|   USDTFEB  |   0xCAA9 |    51881 |        10000 | Feb$T 0.0001 |
|   USDCFEB  |   0xCA95 |    51861 |        10000 | Feb$C 0.0001 |
|   XBTMAR   |   0xC802 |    51202 |        10000 |  MarɃ 0.0001 |
|   BCHMAR   |   0xC816 |    51222 |        10000 | MarɃC 0.0001 |
|   ETHMAR   |   0xC82A |    51242 |        10000 |  MarΞ 0.0001 |
|   USDTMAR  |   0xCAAA |    51882 |        10000 | Mar$T 0.0001 |
|   USDCMAR  |   0xCA96 |    51862 |        10000 | Mar$C 0.0001 |
|   XBTAPR   |   0xC803 |    51203 |        10000 |  AprɃ 0.0001 |
|   BCHAPR   |   0xC817 |    51223 |        10000 | AprɃC 0.0001 |
|   ETHAPR   |   0xC82B |    51243 |        10000 |  AprΞ 0.0001 |
|   USDTAPR  |   0xCAAB |    51883 |        10000 | Apr$T 0.0001 |
|   USDCAPR  |   0xCA97 |    51863 |        10000 | Apr$C 0.0001 |
|   XBTMAY   |   0xC804 |    51204 |        10000 |  MayɃ 0.0001 |
|   BCHMAY   |   0xC818 |    51224 |        10000 | MayɃC 0.0001 |
|   ETHMAY   |   0xC82C |    51244 |        10000 |  MayΞ 0.0001 |
|   USDTMAY  |   0xCAAC |    51884 |        10000 | May$T 0.0001 |
|   USDCMAY  |   0xCA98 |    51864 |        10000 | May$C 0.0001 |
|   XBTJUN   |   0xC805 |    51205 |        10000 |  JunɃ 0.0001 |
|   BCHJUN   |   0xC819 |    51225 |        10000 | JunɃC 0.0001 |
|   ETHJUN   |   0xC82D |    51245 |        10000 |  JunΞ 0.0001 |
|   USDTJUN  |   0xCAAD |    51885 |        10000 | Jun$T 0.0001 |
|   USDCJUN  |   0xCA99 |    51865 |        10000 | Jun$C 0.0001 |
|   XBTJUL   |   0xC806 |    51206 |        10000 |  JulɃ 0.0001 |
|   BCHJUL   |   0xC81A |    51226 |        10000 | JulɃC 0.0001 |
|   ETHJUL   |   0xC82E |    51246 |        10000 |  JulΞ 0.0001 |
|   USDTJUL  |   0xCAAE |    51886 |        10000 | Jul$T 0.0001 |
|   USDCJUL  |   0xCA9A |    51866 |        10000 | Jul$C 0.0001 |
|   XBTAUG   |   0xC807 |    51207 |        10000 |  AugɃ 0.0001 |
|   BCHAUG   |   0xC81B |    51227 |        10000 | AugɃC 0.0001 |
|   ETHAUG   |   0xC82F |    51247 |        10000 |  AugΞ 0.0001 |
|   USDTAUG  |   0xCAAF |    51887 |        10000 | Aug$T 0.0001 |
|   USDCAUG  |   0xCA9B |    51867 |        10000 | Aug$C 0.0001 |
|   XBTSEP   |   0xC808 |    51208 |        10000 |  SepɃ 0.0001 |
|   BCHSEP   |   0xC81C |    51228 |        10000 | SepɃC 0.0001 |
|   ETHSEP   |   0xC830 |    51248 |        10000 |  SepΞ 0.0001 |
|   USDTSEP  |   0xCAB0 |    51888 |        10000 | Sep$T 0.0001 |
|   USDCSEP  |   0xCA9C |    51868 |        10000 | Sep$C 0.0001 |
|   XBTOCT   |   0xC809 |    51209 |        10000 |  OctɃ 0.0001 |
|   BCHOCT   |   0xC81D |    51229 |        10000 | OctɃC 0.0001 |
|   ETHOCT   |   0xC831 |    51249 |        10000 |  OctΞ 0.0001 |
|   USDTOCT  |   0xCAB1 |    51889 |        10000 | Oct$T 0.0001 |
|   USDCOCT  |   0xCA9D |    51869 |        10000 | Oct$C 0.0001 |
|   XBTNOV   |   0xC80A |    51210 |        10000 |  NovɃ 0.0001 |
|   BCHNOV   |   0xC81E |    51230 |        10000 | NovɃC 0.0001 |
|   ETHNOV   |   0xC832 |    51250 |        10000 |  NovΞ 0.0001 |
|   USDTNOV  |   0xCAB2 |    51890 |        10000 | Nov$T 0.0001 |
|   USDCNOV  |   0xCA9E |    51870 |        10000 | Nov$C 0.0001 |
|   XBTDEC   |   0xC80B |    51211 |        10000 |  DecɃ 0.0001 |
|   BCHDEC   |   0xC81F |    51231 |        10000 | DecɃC 0.0001 |
|   ETHDEC   |   0xC833 |    51251 |        10000 |  DecΞ 0.0001 |
|   USDTDEC  |   0xCAB3 |    51891 |        10000 | Dec$T 0.0001 |
|   USDCDEC  |   0xCA9F |    51871 |        10000 | Dec$C 0.0001 |

### Examples

| Logical Amount | Integer Encoding |
|---------------:|-----------------:|
|       Ƀ12.3456 |           123456 |
|        $T1.654 |            16540 |
|           Ƀ1.5 |            15000 |
|           $C20 |           200000 |


## Prices

Prices transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset pair.

|    Asset Pair     | Scale Factor |
|:-----------------:|-------------:|
|      XBT:USDT     |        10000 |
|      BCH:USDT     |        10000 |
|      ETH:USDT     |        10000 |
|      USDC:USDT    |        10000 |
|      FLEX:USDT    |        10000 |
|   XBTJAN:USDTJAN  |        10000 |
|   BCHJAN:USDTJAN  |        10000 |
|   ETHJAN:USDTJAN  |        10000 |
|   USDCJAN:USDTJAN |        10000 |
|   XBTFEB:USDTFEB  |        10000 |
|   BCHFEB:USDTFEB  |        10000 |
|   ETHFEB:USDTFEB  |        10000 |
|  USDCFEB:USDTFEB  |        10000 |
|   XBTMAR:USDTMAR  |        10000 |
|   BCHMAR:USDTMAR  |        10000 |
|   ETHMAR:USDTMAR  |        10000 |
|  USDCMAR:USDTMAR  |        10000 |
|  XBTAPR:USDTAPR   |        10000 |
|   BCHAPR:USDTAPR  |        10000 |
|   ETHAPR:USDTAPR  |        10000 |
|  USDCAPR:USDTAPR  |        10000 |
|  XBTMAY:USDTMAY   |        10000 |
|   BCHMAY:USDTMAY  |        10000 |
|   ETHMAY:USDTMAY  |        10000 |
|  USDCMAY:USDTMAY  |        10000 |
|  XBTJUN:USDTJUN   |        10000 |
|   BCHJUN:USDTJUN  |        10000 |
|   ETHJUN:USDTJUN  |        10000 |
|  USDCJUN:USDTJUN  |        10000 |
|  XBTJUL:USDTJUL   |        10000 |
|   BCHJUL:USDTJUL  |        10000 |
|   ETHJUL:USDTJUL  |        10000 |
|  USDCJUL:USDTJUL  |        10000 |
|  XBTAUG:USDTAUG   |        10000 |
|   BCHAUG:USDTAUG  |        10000 |
|   ETHAUG:USDTAUG  |        10000 |
|  USDCAUG:USDTAUG  |        10000 |
|  XBTSEP:USDTSEP   |        10000 |
|   BCHSEP:USDTSEP  |        10000 |
|   ETHSEP:USDTSEP  |        10000 |
|  USDCSEP:USDTSEP  |        10000 |
|  XBTOCT:USDTOCT   |        10000 |
|   BCHOCT:USDTOCT  |        10000 |
|   ETHOCT:USDTOCT  |        10000 |
|  USDCOCT:USDTOCT  |        10000 |
|  XBTNOV:USDTNOV   |        10000 |
|   BCHNOV:USDTNOV  |        10000 |
|   ETHNOV:USDTNOV  |        10000 |
|  USDCNOV:USDTNOV  |        10000 |
|  XBTDEC:USDTDEC   |        10000 |
|   BCHDEC:USDTDEC  |        10000 |
|   ETHDEC:USDTDEC  |        10000 |
|  USDCDEC:USDTDEC  |        10000 |

### Examples

| Logical Price | Integer Encoding |
|--------------:|-----------------:|
|    $T4443/XBT |         44430000 |
|  $T1.011/USDC |            10110 |


## Tick Size

The Tick Size applied per asset pair as follows. 

Note that bid prices are always rounded down and ask prices are always rounded up so as to ensure that a user never receives a less favourable price on their order than they requested.

|    Asset Pair     |   Tick Size  |
|:-----------------:|-------------:|
|      XBT:USDT     |            1 |
|      BCH:USDT     |         0.25 |
|      ETH:USDT     |          0.1 |
|      USDC:USDT    |        0.001 |
|      FLEX:USDT    |        0.005 |
|   XBTJAN:USDTJAN  |            1 |
|   BCHJAN:USDTJAN  |         0.25 |
|   ETHJAN:USDTJAN  |          0.1 |
|   USDCJAN:USDTJAN |        0.001 |
|   XBTFEB:USDTFEB  |            1 |
|   BCHFEB:USDTFEB  |         0.25 |
|   ETHFEB:USDTFEB  |          0.1 |
|  USDCFEB:USDTFEB  |        0.001 |
|   XBTMAR:USDTMAR  |            1 |
|   BCHMAR:USDTMAR  |         0.25 |
|   ETHMAR:USDTMAR  |          0.1 |
|  USDCMAR:USDTMAR  |        0.001 |
|  XBTAPR:USDTAPR   |            1 |
|   BCHAPR:USDTAPR  |         0.25 |
|   ETHAPR:USDTAPR  |          0.1 |
|  USDCAPR:USDTAPR  |        0.001 |
|  XBTMAY:USDTMAY   |            1 |
|   BCHMAY:USDTMAY  |         0.25 |
|   ETHMAY:USDTMAY  |          0.1 |
|  USDCMAY:USDTMAY  |        0.001 |
|  XBTJUN:USDTJUN   |            1 |
|   BCHJUN:USDTJUN  |         0.25 |
|   ETHJUN:USDTJUN  |          0.1 |
|  USDCJUN:USDTJUN  |        0.001 |
|  XBTJUL:USDTJUL   |            1 |
|   BCHJUL:USDTJUL  |         0.25 |
|   ETHJUL:USDTJUL  |          0.1 |
|  USDCJUL:USDTJUL  |        0.001 |
|  XBTAUG:USDTAUG   |            1 |
|   BCHAUG:USDTAUG  |         0.25 |
|   ETHAUG:USDTAUG  |          0.1 |
|  USDCAUG:USDTAUG  |        0.001 |
|  XBTSEP:USDTSEP   |            1 |
|   BCHSEP:USDTSEP  |         0.25 |
|   ETHSEP:USDTSEP  |          0.1 |
|  USDCSEP:USDTSEP  |        0.001 |
|  XBTOCT:USDTOCT   |            1 |
|   BCHOCT:USDTOCT  |         0.25 |
|   ETHOCT:USDTOCT  |          0.1 |
|  USDCOCT:USDTOCT  |        0.001 |
|  XBTNOV:USDTNOV   |            1 |
|   BCHNOV:USDTNOV  |         0.25 |
|   ETHNOV:USDTNOV  |          0.1 |
|  USDCNOV:USDTNOV  |        0.001 |
|  XBTDEC:USDTDEC   |            1 |
|   BCHDEC:USDTDEC  |         0.25 |
|   ETHDEC:USDTDEC  |          0.1 |
|  USDCDEC:USDTDEC  |        0.001 |

### Examples

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Sell 0.0001 XBT @ 4000.0001 USDT |   Sell 0.0001 XBT @ 4001 USDT   |
|      Qty:-1, Price:40000001      |      Qty:-1, Price:40010000     |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Buy 0.001 ETH @ 160.19 USDT      |    Buy 0.001 ETH @ 160.1 USDT   |
|      Qty:10, Price:1601900       |      Qty:10, Price:1601000      |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Buy 1.5 FLEX @ 10.206 USDT       |    Buy 1.5 FLEX @ 10.205 USDT   |
|      Qty:15000, Price:102060     |      Qty:15000, Price:102050    |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Sell 1.0001 BCH @ 268.76 USDT    |   Sell 1.0001 BCH @ 269.00 USDT |
|      Qty:10001, Price: 2687600   |     Qty:10001, Price:2690000    |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Buy  1.1234 XBT @ 3999.9999 USDT |   Buy  1.1234 XBT @ 3999 USDT   |
|     Qty:11234, Price:39999999    |    Qty:11234, Price:39990000    |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
|  Sell 1.0001 USDC @ 1.0001 USDT  |  Sell 1.0001 USDC @ 1.001 USDT  |
|     Qty:-10001, Price:10001      |     Qty:-10001, Price:10010     |

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
|  Buy  1.0019 USDC @ 1.1299 USDT  |  Buy  1.0019 USDC @ 1.129 USDT  |
|     Qty:10019, Price:11299       |    Qty:10019, Price:11290       |

