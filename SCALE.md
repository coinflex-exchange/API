# Scaling


## Amounts

Asset quantities and totals transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset type.

| Asset Type | ID (Hex) | ID (Dec) | Scale Factor |  Atomic Unit |
|:----------:|---------:|---------:|-------------:|-------------:|
|     XBT    |   0xF800 |    63488 |        10000 |      Ƀ0.0001 |
|     BCH    |   0xF808 |    63496 |        10000 |     ɃC0.0001 |
|     USDC   |   0xFF02 |    65282 |         1000 |       $0.001 |
|     USDT   |   0xFF03 |    65283 |         1000 |       $0.001 |
|   XBTJAN   |   0xC800 |    51200 |        10000 |   JanɃ0.0001 |
|   USDTJAN  |   0xCAA8 |    51880 |         1000 |   Jan$T0.001 |
|   USDCJAN  |   0xCA80 |    51860 |         1000 |   Jan$C0.001 |
|   XBTFEB   |   0xC801 |    51201 |        10000 |   FebɃ0.0001 |
|   USDTFEB  |   0xCAA9 |    51881 |         1000 |   Feb$T0.001 |
|   USDCFEB  |   0xCA81 |    51861 |         1000 |   Feb$C0.001 |
|   XBTMAR   |   0xC802 |    51202 |        10000 |   MarɃ0.0001 |
|   USDTMAR  |   0xCAAA |    51882 |         1000 |   Mar$T0.001 |
|   USDCMAR  |   0xCA82 |    51862 |         1000 |   Mar$C0.001 |
|   XBTAPR   |   0xC803 |    51203 |        10000 |   AprɃ0.0001 |
|   USDTAPR  |   0xCAAB |    51883 |         1000 |   Apr$T0.001 |
|   USDCAPR  |   0xCA83 |    51863 |         1000 |   Apr$C0.001 |
|   XBTMAY   |   0xC804 |    51204 |        10000 |   MayɃ0.0001 |
|   USDTMAY  |   0xCAAC |    51884 |         1000 |   May$T0.001 |
|   USDCMAY  |   0xCA84 |    51864 |         1000 |   May$C0.001 |
|   XBTJUN   |   0xC805 |    51205 |        10000 |   JunɃ0.0001 |
|   USDTJUN  |   0xCAAD |    51885 |         1000 |   Jun$T0.001 |
|   USDCJUN  |   0xCA85 |    51865 |         1000 |   Jun$C0.001 |
|   XBTJUL   |   0xC806 |    51206 |        10000 |   JulɃ0.0001 |
|   USDTJUL  |   0xCAAE |    51886 |         1000 |   Jul$T0.001 |
|   USDCJUL  |   0xCA86 |    51866 |         1000 |   Jul$C0.001 |
|   XBTAUG   |   0xC807 |    51207 |        10000 |   AugɃ0.0001 |
|   USDTAUG  |   0xCAAF |    51887 |         1000 |   Aug$T0.001 |
|   USDCAUG  |   0xCA87 |    51867 |         1000 |   Aug$C0.001 |
|   XBTSEP   |   0xC808 |    51208 |        10000 |   SepɃ0.0001 |
|   USDTSEP  |   0xCAB0 |    51888 |         1000 |   Sep$T0.001 |
|   USDCSEP  |   0xCA88 |    51868 |         1000 |   Sep$C0.001 |
|   XBTOCT   |   0xC809 |    51209 |        10000 |   OctɃ0.0001 |
|   USDTOCT  |   0xCAB1 |    51889 |         1000 |   Oct$T0.001 |
|   USDCOCT  |   0xCA89 |    51869 |         1000 |   Oct$C0.001 |
|   XBTNOV   |   0xC80A |    51210 |        10000 |   NovɃ0.0001 |
|   USDTNOV  |   0xCAB2 |    51890 |         1000 |   Nov$T0.001 |
|   USDCNOV  |   0xCA8A |    51870 |         1000 |   Nov$C0.001 |
|   XBTDEC   |   0xC80B |    51211 |        10000 |   DecɃ0.0001 |
|   USDTDEC  |   0xCAB3 |    51891 |         1000 |   Dec$T0.001 |
|   USDCDEC  |   0xCA8B |    51871 |         1000 |   Dec$C0.001 |

### Examples

| Logical Amount | Integer Encoding |
|---------------:|-----------------:|
|       Ƀ12.3456 |           123456 |
|       £9876.54 |           987654 |
|           Ƀ1.5 |            15000 |
|            £20 |             2000 |


## Prices

Prices transmitted via the CoinFLEX API are encoded as integers with an implicit scale factor that depends on the particular asset pair.

|    Asset Pair     | Scale Factor |
|:-----------------:|-------------:|
|      XBT:USDT     |          100 |
|      USDT:USDC    |          100 |
|   XBTJAN:USDTJAN  |          100 |
|   USDTJAN:USDCJAN |          100 |
|   XBTFEB:USDTFEB  |          100 |
|   USDTFEB:USDCFEB |          100 |
|   XBTMAR:USDTMAR  |          100 |
|   USDTMAR:USDCMAR |          100 |
|   XBTAPR:USDTAPR  |          100 |
|   USDTAPR:USDCAPR |          100 |
|   XBTMAY:USDTMAY  |          100 |
|   USDTMAY:USDCMAY |          100 |
|   XBTJUN:USDTJUN  |          100 |
|   USDTJUN:USDCJUN |          100 |
|   XBTJUL:USDTJUL  |          100 |
|   USDTJUL:USDCJUL |          100 |
|   XBTAUG:USDTAUG  |          100 |
|   USDTAUG:USDCAUG |          100 |
|   XBTSEP:USDTSEP  |          100 |
|   USDTSEP:USDCSEP |          100 |
|   XBTOCT:USDTOCT  |          100 |
|   USDTOCT:USDCOCT |          100 |
|   XBTNOV:USDTNOV  |          100 |
|   USDTNOV:USDCNOV |          100 |
|   XBTDEC:USDTDEC  |          100 |
|   USDTDEC:USDCDEC |          100 |

### Examples

| Logical Price | Integer Encoding |
|--------------:|-----------------:|
|   £543.21/XBT |            54321 |
|     £1000/XBT |           100000 |

