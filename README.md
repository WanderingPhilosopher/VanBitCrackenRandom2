# VanBitCrackenRandom2
The Newest Version of VanBitCracken...VBCr
This program is really only intended for the BTC Challenge. However, you can use it to generate your own personal BTC address and use it.
It is a spinoff of JLP's original VanitySearch.
Supports a simple -bits flag and Begin and End Range (-begr and -endr) flags. New version also supports full address with newer RTX cards. It has been tested on Windows 10 and Windows 11 on RTX 30xx cards, RTX 20xx cards and a GTX 1660 Ti card.
(Program will be released after additional testing)

Batch file settings example using -begr and -endr flags:
```
VBCr -t 0 -gpu -gpuId 0 -begr 2000000000000000 -endr 3000000000000000 -r 2400 -o 66BitChallengeKey.txt 13zb1hQbWVsc2S7ZTZnP2G4undNNpdh5so
```

Batch file settings example using -bits flag:
```
VBCr -t 0 -gpu -gpuId 0 -bits 66 -r 2400 -o 66BitChallengeKey.txt 13zb1hQbWVsc2S7ZTZnP2G4undNNpdh5so
```

