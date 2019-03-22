# Scaling


## Amounts

Asset quantities and totals transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset type. 

| Asset Type | ID (Hex) | ID (Dec) | Scale Factor |  Atomic Unit |
|:----------:|---------:|---------:|-------------:|-------------:|
|     XBT    |   0xF800 |    63488 |        10000 |     Ƀ 0.0001 |
|     USDC   |   0xFF02 |    65282 |         1000 |     $C 0.001 |
|     USDT   |   0xFF03 |    65283 |         1000 |     $T 0.001 |
|  XBTJAN    |   0xC800 |    51200 |        10000 |  JanɃ 0.0001 |
|  USDTJAN   |   0xCAA8 |    51880 |         1000 |  Jan$T 0.001 |
|  USDCJAN   |   0xCA94 |    51860 |         1000 |  Jan$C 0.001 |
|   XBTFEB   |   0xC801 |    51201 |        10000 |  FebɃ 0.0001 |
|   USDTFEB  |   0xCAA9 |    51881 |         1000 |  Feb$T 0.001 |
|   USDCFEB  |   0xCA95 |    51861 |         1000 |  Feb$C 0.001 |
|   XBTMAR   |   0xC802 |    51202 |        10000 |  MarɃ 0.0001 |
|   USDTMAR  |   0xCAAA |    51882 |         1000 |  Mar$T 0.001 |
|   USDCMAR  |   0xCA96 |    51862 |         1000 |  Mar$C 0.001 |
|   XBTAPR   |   0xC803 |    51203 |        10000 |  AprɃ 0.0001 |
|   USDTAPR  |   0xCAAB |    51883 |         1000 |  Apr$T 0.001 |
|   USDCAPR  |   0xCA97 |    51863 |         1000 |  Apr$C 0.001 |
|   XBTMAY   |   0xC804 |    51204 |        10000 |  MayɃ 0.0001 |
|   USDTMAY  |   0xCAAC |    51884 |         1000 |  May$T 0.001 |
|   USDCMAY  |   0xCA98 |    51864 |         1000 |  May$C 0.001 |
|   XBTJUN   |   0xC805 |    51205 |        10000 |  JunɃ 0.0001 |
|   USDTJUN  |   0xCAAD |    51885 |         1000 |  Jun$T 0.001 |
|   USDCJUN  |   0xCA99 |    51865 |         1000 |  Jun$C 0.001 |
|   XBTJUL   |   0xC806 |    51206 |        10000 |  JulɃ 0.0001 |
|   USDTJUL  |   0xCAAE |    51886 |         1000 |  Jul$T 0.001 |
|   USDCJUL  |   0xCA9A |    51866 |         1000 |  Jul$C 0.001 |
|   XBTAUG   |   0xC807 |    51207 |        10000 |  AugɃ 0.0001 |
|   USDTAUG  |   0xCAAF |    51887 |         1000 |  Aug$T 0.001 |
|   USDCAUG  |   0xCA9B |    51867 |         1000 |  Aug$C 0.001 |
|   XBTSEP   |   0xC808 |    51208 |        10000 |  SepɃ 0.0001 |
|   USDTSEP  |   0xCAB0 |    51888 |         1000 |  Sep$T 0.001 |
|   USDCSEP  |   0xCA9C |    51868 |         1000 |  Sep$C 0.001 |
|   XBTOCT   |   0xC809 |    51209 |        10000 |  OctɃ 0.0001 |
|   USDTOCT  |   0xCAB1 |    51889 |         1000 |  Oct$T 0.001 |
|   USDCOCT  |   0xCA9D |    51869 |         1000 |  Oct$C 0.001 |
|   XBTNOV   |   0xC80A |    51210 |        10000 |  NovɃ 0.0001 |
|   USDTNOV  |   0xCAB2 |    51890 |         1000 |  Nov$T 0.001 |
|   USDCNOV  |   0xCA9E |    51870 |         1000 |  Nov$C 0.001 |
|   XBTDEC   |   0xC80B |    51211 |        10000 |  DecɃ 0.0001 |
|   USDTDEC  |   0xCAB3 |    51891 |         1000 |  Dec$T 0.001 |
|   USDCDEC  |   0xCA9F |    51871 |         1000 |  Dec$C 0.001 |

### Examples

| Logical Amount | Integer Encoding |
|---------------:|-----------------:|
|       Ƀ12.3456 |           123456 |
|      $T987.654 |           987654 |
|           Ƀ1.5 |            15000 |
|           $C20 |            20000 |


## Prices

Prices transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset pair.

|    Asset Pair     | Scale Factor |
|:-----------------:|-------------:|
|      XBT:USDT     |         1000 |
|      USDC:USDT    |         1000 |
|   XBTJAN:USDTJAN  |         1000 |
|   USDTJAN:USDCJAN |         1000 |
|   XBTFEB:USDTFEB  |         1000 |
|  USDTFEB:USDCFEB  |         1000 |
|   XBTMAR:USDTMAR  |         1000 |
|  USDTMAR:USDCMAR  |         1000 |
|  XBTAPR:USDTAPR   |         1000 |
|  USDTAPR:USDCAPR  |         1000 |
|  XBTMAY:USDTMAY   |         1000 |
|  USDTMAY:USDCMAY  |         1000 |
|  XBTJUN:USDTJUN   |         1000 |
|  USDTJUN:USDCJUN  |         1000 |
|  XBTJUL:USDTJUL   |         1000 |
|  USDTJUL:USDCJUL  |         1000 |
|  XBTAUG:USDTAUG   |         1000 |
|  USDTAUG:USDCAUG  |         1000 |
|  XBTSEP:USDTSEP   |         1000 |
|  USDTSEP:USDCSEP .|         1000 |
|  XBTOCT:USDTOCT   |         1000 |
|  USDTOCT:USDCOCT  |         1000 |
|  XBTNOV:USDTNOV   |         1000 |
|  USDTNOV:USDCNOV  |         1000 |
|  XBTDEC:USDTDEC   |         1000 |
|  USDTDEC:USDCDEC  |         1000 |


### Examples

| Logical Price | Integer Encoding |
|--------------:|-----------------:|
| $T543.211/XBT |           543211 |
|      $T1/USDC |             1000 |

