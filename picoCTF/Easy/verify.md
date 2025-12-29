# Verify
#### debug info: [u:953389 e: p: c:450 i:296132]

## Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

# Approach
Upon connecting the server, we can ls to see what files we have to work with.
```
checksum.txt decrypt.sh files
```
The checksum provided in the challenge is the same as the one found in the text file. Opening file, we can see a large amount of encrypted files:
```
00011a60  0xknvebh  2emuPVOb  3Vs8v8kW  5gxjbRbh  7ye3lPVb  9KIFXofB  AiUxYmz8  Bh5xju3q  ClWGbsxu  FJBePm2b  GufDk3Mb  HqxLJgMp  Izq2bmb5  KbGMgDus  MPeS8YHI  OIYZeUCB  QbiQCWZr  RPVIP1xx  T6AHhqdE  U3BoYTr9  WBpZ7iz6  YKQLrxBm  aHFaEXKf  c3Z3JN0m  e2umkBxy  fZHEnAvZ  iGwCDzaU  jcMzi4VO  knHTEYup  m3bsNhyN  nrwKQbJk  pb1E0Y3Z  qWv24Da7  sAy34VP4  uMpXxbqr  vsGKdf0J  yYRsKiUO
022cvpdN  1kTWMoOI  2gP5wDgq  3qDKN57P  5rHRNllE  870YaC5g  9pluLfgA  AmsN0Lkj  C1kYNpjq  DCn7KnqG  FLsBEmlR  HDLWGApz  IDQQR4nq  J16J63tC  KlqDh1ZQ  N8vFOGDF  OPqDbOIH  QcIkjhJ0  RQWaIGxG  TPBDRCiJ  UDI6pN8S  WjY12GNe  YdTZkUcM  aIz8E0Iy  cIDWC9cb  e5b74XZq  g2E6RkkX  iILvZZya  jdYv9CQ3  ksIZWNZR  mWWBZCgt  oNnB9jru  pnycz11G  qZ7TLGA0  sKi8TaSn  uUI8gJNi  w1XGgnr9  yg7uBent
04nLilRD  1mGlW6Ts  2w5vJlLG  4CwloraZ  63MqIIVV  8Shyigig  ADMuzktV  ArUDDIQ3  CF4c5xR8  DSKHZ66z  FOxKdaVP  HIeYL84k  IITtRrrR  JVEoV1Bn  L58tTvhF  NC6PZdoL  Oe0SOw16  QgmCuMSV  RVejZvvP  TRyxUwzw  UF1urDfG  Ww6oTYL8  Z2rLXuyp  afLk75aO  dDoFZTXh  eFlmUkb6  g2nu6vlR  ih6levXk  jzmPaO2D  lZiPMwX4  mdFDpW9k  oi96tAtc  q53EoTzu  qojIz6XF  sNI2Q6oa  ugeJ5RN3  w8DmFhfg  zYz6howf
0MT2Wrui  2JKdkggW  2yMtx5qd  4XqPqs6B  64nJlBLv  8d0Ncqme  AEJxVlNY  Azqf6EEw  CGkVyMxT  Dmsex2Ug  FtMorZ65  HJIPzwjJ  IbMiqCHJ  Jcwq4RxP  L7gltlCF  NS9xPzIA  OnCx4O4u  Qxrlj2uk  RdYwRe68  TXsLzqsp  UUiDNDlO  X5rRZ32p  ZWIiY84t  b9YCg3Tz  dKYP6pnk  eNfM7vPK  gLAo3J0D  j1v0LBVe  kDPV8ASY  lcYptJNC  n2XnM9Nc  oiy29oCW  qCTrc9yM  r3HVTaJd  sRaKyq1f  vJDrHtxo  woaiQu5g  zjkul95p
0SGMttmR  2Jr8UtbZ  303DzMmf  4k4veVKp  69JSHBh1  8hKIvq38  AGOEyD4N  B8pBCEvG  CLCyTz85  EBBoQm7M  G7enzzui  HMq6348V  Ie0xOcl5  Jk8UBmcS  LCLocE1C  Ndyi6bnx  P7orF8IR  R3rVsQa8  Rgs7l9CZ  TeaXjOeh  UuC7t9JQ  XGTpUJIw  ZXqAvkcE  bDK7A26M  dKisxYdK  eZ4ehccg  gem657x8  jIlhVDLw  kKVvPy8S  ld12od7V  n7Vs8Bjh  p1LgEQdu  qHwcKaSC  r3Pw8pFI  svmptIxV  vMv1M1qs  wvhWmTPt  zoz7gvVr
0fCDySFB  2K4XCmfE  33CFCJ0y  4sczhCZl  6vgioqew  8rIuGenM  AVdbk5eX  BN0HxLxE  CNvsyU3W  EG1lW2KR  Gcv1H8Qs  HUjCgnh4  IikIpp05  KCL5hW02  LMavH6jA  NxdIqu0S  PECjZnzJ  RAXeLvjl  ScOtAOiZ  TeyHF78l  V2eK2wiC  XJiFKTlc  ZdPbKJh1  bDZN0f4B  deppMJSV  efpcZmHN  hNqXyUX2  jObn0z94  kWjYWiLD  lmr9cGCE  n8r2Ejk9  p5INCxLV  qK35XlHM  r8vIZE1F  tFGQywwr  vWguQ8rQ  xQJV5GcG
0hHVJSPh  2MYWkWLC  36tjTWoF  58BnWcOc  76rj6cv7  91cLOGeN  AXFWLqwI  BOeN3lXR  Cb22Z7FO  EXQ6DiO5  GhrShrXN  HWRVc59e  IlQwVZcY  KKRWbrqC  Lq3dNalV  O5tEUFhw  PpktRW9a  RFLWtody  SwrcVnay  ToT9QPKf  V4VMSZd9  XcmGmkwD  ZyNsHVFW  bcZupFpi  dv0Mm4vr  ekSs7xW4  hZxbAqts  jVkxEmtq  kZ6DTcql  lxv6mvZ6  nldOsSfJ  p5INQHq8  qSn3WAyi  rzYX4BnS  tY2epsSy  vc1wGQhn  xlqXOqhL
0mPyFlda  2QpRnoZQ  3KZwXc8s  5bSdd2sp  7j2g9w9w  9DNfzhUK  AdzCNBlC  BdO65Tk4  Ce5TrzJu  F6yHlWpt  Gtk4Kn9w  Hmr54gXd  ItYR0Da2  KUIfl2m7  LrYo1dnu  OH3906gp  QHv46Plh  RHjAw3hj  T5IkmqtJ  TtPblPd6  VhBNGSYV  YAZlvEou  aGVRRt1d  bjtBJwTc  e1x51vcc  eknrQKQh  haNCaZmC  jVlaDg4q  kbumrMcy  m1NnTZoo  nnZ33FAt  pXJHJUbH  qV83Dmye  s9TOeOaJ  tuma818A  vjypfsoh  yACAaKqG
```
Trying to use `cat` on any one of these files returns an encrypted string.
Hence, running `decrypt.sh files/*` will run the decryption tool on all files found in the directory - ultimately returning the flag:
```
picoCTF{trust_but_verify_00011a60}
```