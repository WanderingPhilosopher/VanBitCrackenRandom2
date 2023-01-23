# VanBitCrackenRandom2
The Newest Version of VanBitCracken...VBCr

This program is really only intended for the BTC Challenge. However, you can use it to generate your own personal BTC address and use it.

It is a spinoff of JLP's original VanitySearch.

Program supports a simple -bits flag and Begin and End Range (-begr and -endr) flags. New version also supports full address with newer RTX cards. It has been tested on Windows 10 and Windows 11 on RTX 30xx cards, RTX 20xx cards and a GTX 1660 Ti card.

SHA256 Checksum:
```
6083da2c69040c209bc835c0daa5f3dcaaa50f7f1c32151315eff7d99231feb7
```
(Verify by opening cmd, change directory to where file (VBCr.exe) is located, and run CertUtil -hashfile VBCr.exe.exe SHA256


(Program will be released after additional testing)

Batch file settings example using -begr and -endr flags:
```
VBCr -t 0 -gpu -gpuId 0 -begr 2000000000000000 -endr 3000000000000000 -r 2400 -o 66BitChallengeKey.txt 13zb1hQbWVsc2S7ZTZnP2G4undNNpdh5so
```

Batch file settings example using -bits flag:
```
VBCr -t 0 -gpu -gpuId 0 -bits 66 -r 2400 -o 66BitChallengeKey.txt 13zb1hQbWVsc2S7ZTZnP2G4undNNpdh5so
```

printf("Flags");

    printf("VBCr [-check] [-v] [-u] [-b] [-c] [-gpu] [-stop] [-i inputfile]\n");
	printf("             [-gpuId gpuId1[,gpuId2,...]] [-g g1x,g1y,[,g2x,g2y,...]]\n");
	printf("             [-o outputfile] [-m maxFound] [-ps seed] [-s seed] [-t nbThread]\n");
	printf("             [-bits bitsNumber] [-begr BeginRange] [-endr EndRange] [-nosse] [-r rekey] \n");
	printf("             [-check] [-kp] [-sp startPubKey] [-rp privkey partialkeyfile] [prefix]\n\n");
	printf(" prefix: prefix to search (Can contains wildcard '?' or '*')\n");
	printf(" -v: Print version\n");
	printf(" -u: Search uncompressed addresses\n");
	printf(" -b: Search both uncompressed or compressed addresses\n");
	printf(" -c: Case unsensitive search\n");
	printf(" -gpu: Enable gpu calculation\n");
	printf(" -stop: Stop when all prefixes are found\n");
	printf(" -i inputfile: Get list of prefixes to search from specified file\n");
	printf(" -o outputfile: Output results to the specified file; Default is KeysFound.txt\n");
	printf(" -gpu gpuId1,gpuId2,...: List of GPU(s) to use, default is 0\n");
	printf(" -g g1x,g1y,g2x,g2y, ...: Specify GPU(s) kernel gridsize, default is 8*(MP number),128\n");
	printf(" -m: Specify maximun number of prefixes found by each kernel call\n");
	printf(" -s seed: Specify a seed for the base key, default is random\n");
	printf(" -ps seed: Specify a seed concatened with a crypto secure random seed\n");
	printf(" -t threadNumber: Specify number of CPU thread(s). Default is number of core(s)\n");
	printf(" -bits bitsNumber: Specify bit length for private key. Default is 0 bits. -bits overrides -begr/-endr. \n");
	printf(" -begr Begin Range: Specify Beginning Range in which you want to search, ex: 30000000000000000. Must use with -endr\n");
	printf(" -endr End Range: Specify End of Range in which you want to search, ex: 3FFFFFFFFFFFFFFFF. Must use with -begr\n");
	printf(" -dis Private Key info displayed on screen: 0 = off, 1 = on. Default is 0 / off.\n");
	printf(" -drk Display random keys: 0 = off, 1 = on. Default is 0 / off.\n");
	printf(" -nosse: Disable SSE hash function\n");
	printf(" -l: List cuda enabled devices\n");
	printf(" -check: Check CPU and GPU kernel vs CPU\n");
	printf(" -cp privKey: Compute public key (privKey in hex hormat)\n");
	printf(" -ca pubKey: Compute address (pubKey in hex hormat)\n");
	printf(" -kp: Generate key pair\n");
	printf(" -rp privkey partialkeyfile: Reconstruct final private key(s) from partial key(s) info.\n");
	printf(" -sp startPubKey: Start the search with a pubKey (for private key splitting)\n");
	printf(" -r rekey: Rekey interval in MegaKey (millions). Default is disabled / 0.\n");

New flags: -dis = will show private key info on screen if found. -drk will display a few random keys on each rekey
Example usage with -bits, -dis, -drk
Batch file settings:
```
VBCr.exe -stop -begr 8000000 -endr fffffff -t 3 -dis 1 -r 30 -drk 1 12jbtzBb54r97TCwW3G1gCFoumpckRAPdY
pause
```

Results
```
VBCr v2.00
 Search For: 12jbtzBb54r97TCwW3G1gCFoumpckRAPdY [Compressed]
 Started on: Sun Jan 22 20:21:55 2023
 Randomness: New Random Keys Every 30 Mkeys
  Beg Range: 8000000 (28 bit)
  End Range: FFFFFFF (28 bit)
  Rng Width: 7FFFFFF (27 bit)
CPU Threads: 3

Random Key :  FABEC30
Random Key :  A1ECC58
 [00:00:00:04 Run Time][Total 8.64 MK/s][GPU 0.00 MK/s][Keys 35,030,016][Found 0][Rekeys: 0]
Random Key :  CF0A7FB
Random Key :  C2AA2EF
 [00:00:00:08 Run Time][Total 8.22 MK/s][GPU 0.00 MK/s][Keys 66,820,096][Found 0][Rekeys: 1]
Random Key :  AD3045D
Random Key :  9EF1989
 [00:00:00:12 Run Time][Total 8.00 MK/s][GPU 0.00 MK/s][Keys 97,549,312][Found 0][Rekeys: 2]
Random Key :  C69AA78
Random Key :  C12D635
 [00:00:00:16 Run Time][Total 7.93 MK/s][GPU 0.00 MK/s][Keys 128,915,456][Found 0][Rekeys: 3]
Random Key :  8F2D343
Random Key :  BBAC6E6
 [00:00:00:20 Run Time][Total 7.73 MK/s][GPU 0.00 MK/s][Keys 160,857,088][Found 0][Rekeys: 4]
Random Key :  AEFBEE1
Random Key :  D83BB40
Random Key :  E6213A7

PubAddress: 12jbtzBb54r97TCwW3G1gCFoumpckRAPdY
Priv (WIF): p2pkh: KwDiBf89QgGbjEhKnhXJuH7LrciVrZi3qYjgd9M82GSgY8p5EkUe
Priv (HEX): D916CE8 (28 bit)
```

Resuts turning off -dis and -drk (private key info is saved to output file):

Batch file settings:
```
VBCr.exe -stop -begr 8000000 -endr fffffff -t 3 -dis 0 -r 30 -drk 0 12jbtzBb54r97TCwW3G1gCFoumpckRAPdY
pause
```
Results:
```
VBCr v2.00
 Search For: 12jbtzBb54r97TCwW3G1gCFoumpckRAPdY [Compressed]
 Started on: Sun Jan 22 20:26:13 2023
 Randomness: New Random Keys Every 30 Mkeys
  Beg Range: 8000000 (28 bit)
  End Range: FFFFFFF (28 bit)
  Rng Width: 7FFFFFF (27 bit)
CPU Threads: 3
 [00:00:00:20 Run Time][Total 7.63 MK/s][GPU 0.00 MK/s][Keys 158,656,512][Found 0][Rekeys: 4]
```
