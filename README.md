# VanBitCrackenRandom2
The Newest Version of VanBitCracken...VBCr

This program is really only intended for the BTC Challenge. However, you can use it to generate your own personal BTC address and use it.

It is a spinoff of JLP's original VanitySearch.

Program supports a simple -bits flag and Begin and End Range (-begr and -endr) flags. New version also supports full address with newer RTX cards. It has been tested on Windows 10 and Windows 11 on RTX 30xx cards, RTX 20xx cards and a GTX 1660 Ti card.

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
