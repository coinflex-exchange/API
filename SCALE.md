# Scaling


## Amounts

Asset quantities and totals transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset type. All assets have now been set with a scaling factor of 10000 (i.e. 4 decimal places).

| Asset Type | ID (Hex) | ID (Dec) | Scale Factor |  Atomic Unit |
|:----------:|---------:|---------:|-------------:|-------------:|
|     XBT    |   0xF800 |    63488 |        10000 |     Ƀ 0.0001 |
|     USDC   |   0xFF02 |    65282 |        10000 |    $C 0.0001 |
|     USDT   |   0xFF03 |    65283 |        10000 |    $T 0.0001 |
|  XBTJAN    |   0xC800 |    51200 |        10000 |  JanɃ 0.0001 |
|  USDTJAN   |   0xCAA8 |    51880 |        10000 | Jan$T 0.0001 |
|  USDCJAN   |   0xCA94 |    51860 |        10000 | Jan$C 0.0001 |
|   XBTFEB   |   0xC801 |    51201 |        10000 |  FebɃ 0.0001 |
|   USDTFEB  |   0xCAA9 |    51881 |        10000 | Feb$T 0.0001 |
|   USDCFEB  |   0xCA95 |    51861 |        10000 | Feb$C 0.0001 |
|   XBTMAR   |   0xC802 |    51202 |        10000 |  MarɃ 0.0001 |
|   USDTMAR  |   0xCAAA |    51882 |        10000 | Mar$T 0.0001 |
|   USDCMAR  |   0xCA96 |    51862 |        10000 | Mar$C 0.0001 |
|   XBTAPR   |   0xC803 |    51203 |        10000 |  AprɃ 0.0001 |
|   USDTAPR  |   0xCAAB |    51883 |        10000 | Apr$T 0.0001 |
|   USDCAPR  |   0xCA97 |    51863 |        10000 | Apr$C 0.0001 |
|   XBTMAY   |   0xC804 |    51204 |        10000 |  MayɃ 0.0001 |
|   USDTMAY  |   0xCAAC |    51884 |        10000 | May$T 0.0001 |
|   USDCMAY  |   0xCA98 |    51864 |        10000 | May$C 0.0001 |
|   XBTJUN   |   0xC805 |    51205 |        10000 |  JunɃ 0.0001 |
|   USDTJUN  |   0xCAAD |    51885 |        10000 | Jun$T 0.0001 |
|   USDCJUN  |   0xCA99 |    51865 |        10000 | Jun$C 0.0001 |
|   XBTJUL   |   0xC806 |    51206 |        10000 |  JulɃ 0.0001 |
|   USDTJUL  |   0xCAAE |    51886 |        10000 | Jul$T 0.0001 |
|   USDCJUL  |   0xCA9A |    51866 |        10000 | Jul$C 0.0001 |
|   XBTAUG   |   0xC807 |    51207 |        10000 |  AugɃ 0.0001 |
|   USDTAUG  |   0xCAAF |    51887 |        10000 | Aug$T 0.0001 |
|   USDCAUG  |   0xCA9B |    51867 |        10000 | Aug$C 0.0001 |
|   XBTSEP   |   0xC808 |    51208 |        10000 |  SepɃ 0.0001 |
|   USDTSEP  |   0xCAB0 |    51888 |        10000 | Sep$T 0.0001 |
|   USDCSEP  |   0xCA9C |    51868 |        10000 | Sep$C 0.0001 |
|   XBTOCT   |   0xC809 |    51209 |        10000 |  OctɃ 0.0001 |
|   USDTOCT  |   0xCAB1 |    51889 |        10000 | Oct$T 0.0001 |
|   USDCOCT  |   0xCA9D |    51869 |        10000 | Oct$C 0.0001 |
|   XBTNOV   |   0xC80A |    51210 |        10000 |  NovɃ 0.0001 |
|   USDTNOV  |   0xCAB2 |    51890 |        10000 | Nov$T 0.0001 |
|   USDCNOV  |   0xCA9E |    51870 |        10000 | Nov$C 0.0001 |
|   XBTDEC   |   0xC80B |    51211 |        10000 |  DecɃ 0.0001 |
|   USDTDEC  |   0xCAB3 |    51891 |        10000 | Dec$T 0.0001 |
|   USDCDEC  |   0xCA9F |    51871 |        10000 | Dec$C 0.0001 |

### Examples

| Logical Amount | Integer Encoding |
|---------------:|-----------------:|
|       Ƀ12.3456 |           123456 |
|     $T987.6541 |          9876541 |
|           Ƀ1.5 |            15000 |
|           $C20 |           200000 |


## Prices

Prices transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset pair.

|    Asset Pair     | Scale Factor |
|:-----------------:|-------------:|
|      XBT:USDT     |        10000 |
|      USDC:USDT    |        10000 |
|   XBTJAN:USDTJAN  |        10000 |
|   USDTJAN:USDCJAN |        10000 |
|   XBTFEB:USDTFEB  |        10000 |
|  USDTFEB:USDCFEB  |        10000 |
|   XBTMAR:USDTMAR  |        10000 |
|  USDTMAR:USDCMAR  |        10000 |
|  XBTAPR:USDTAPR   |        10000 |
|  USDTAPR:USDCAPR  |        10000 |
|  XBTMAY:USDTMAY   |        10000 |
|  USDTMAY:USDCMAY  |        10000 |
|  XBTJUN:USDTJUN   |        10000 |
|  USDTJUN:USDCJUN  |        10000 |
|  XBTJUL:USDTJUL   |        10000 |
|  USDTJUL:USDCJUL  |        10000 |
|  XBTAUG:USDTAUG   |        10000 |
|  USDTAUG:USDCAUG  |        10000 |
|  XBTSEP:USDTSEP   |        10000 |
|  USDTSEP:USDCSEP  |        10000 |
|  XBTOCT:USDTOCT   |        10000 |
|  USDTOCT:USDCOCT  |        10000 |
|  XBTNOV:USDTNOV   |        10000 |
|  USDTNOV:USDCNOV  |        10000 |
|  XBTDEC:USDTDEC   |        10000 |
|  USDTDEC:USDCDEC  |        10000 |

### Examples

| Logical Price | Integer Encoding |
|--------------:|-----------------:|
|$T4443.211/XBT |         44432110 |
|      $T1/USDC |            10000 |


## Tick Size

The Tick Size applied per asset pair as follows. 

Note that bid prices are always rounded down and ask prices are always rounded up so as to ensure that a user never receives a less favourable price on their order than they requested.

|    Asset Pair     |   Tick Size  |
|:-----------------:|-------------:|
|      XBT:USDT     |            1 |
|      USDC:USDT    |        0.001 |
|   XBTJAN:USDTJAN  |            1 |
|   USDTJAN:USDCJAN |        0.001 |
|   XBTFEB:USDTFEB  |            1 |
|  USDTFEB:USDCFEB  |        0.001 |
|   XBTMAR:USDTMAR  |            1 |
|  USDTMAR:USDCMAR  |        0.001 |
|  XBTAPR:USDTAPR   |            1 |
|  USDTAPR:USDCAPR  |        0.001 |
|  XBTMAY:USDTMAY   |            1 |
|  USDTMAY:USDCMAY  |        0.001 |
|  XBTJUN:USDTJUN   |            1 |
|  USDTJUN:USDCJUN  |        0.001 |
|  XBTJUL:USDTJUL   |            1 |
|  USDTJUL:USDCJUL  |        0.001 |
|  XBTAUG:USDTAUG   |            1 |
|  USDTAUG:USDCAUG  |        0.001 |
|  XBTSEP:USDTSEP   |            1 |
|  USDTSEP:USDCSEP  |        0.001 |
|  XBTOCT:USDTOCT   |            1 |
|  USDTOCT:USDCOCT  |        0.001 |
|  XBTNOV:USDTNOV   |            1 |
|  USDTNOV:USDCNOV  |        0.001 |
|  XBTDEC:USDTDEC   |            1 |
|  USDTDEC:USDCDEC  |        0.001 |

### Examples

|          Order Placed            |          Order Opened           |
|---------------------------------:|--------------------------------:|
| Sell 0.0001 XBT @ 4000.0001 USDT |   Sell 0.0001 XBT @ 4001 USDT   |
|      Qty:-1, Price:40000001      |      Qty:-1, Price:40010000     |

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

