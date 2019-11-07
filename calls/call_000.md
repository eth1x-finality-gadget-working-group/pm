## Eth1.x Finality Gadget Working Group

### Call 0 Notes

**Video**: https://www.youtube.com/watch?v=ot_io5Xi13M

**Meeting Date/Time**: ????

**Duration**: 41:28

**Attendees**:
- Alex Stokes
- Andrei Ivasko
- Trent Van Epps
- Bryant Eisenbach
- Danny Ryan
- Danno Ferrin
- ????
- Alexey Akhunov 

## Introduction:
[0:00](https://youtu.be/ot_io5Xi13M)

The purpose of this meeting is discussed and a brief introduction into what the finality gadget is is provided. The purpose is to start organizing an effort around the finality gadget and more information about the finality gadget can be found [here](https://medium.com/@ralexstokes/the-finality-gadget-2bf608529e50).

Alex Stokes: Working on the Trinity client at the Ethereum Foundation.
[1:15](https://youtu.be/ot_io5Xi13M?t=76)

Andrei Ivasko: Contributor to the Prysm client and developer at Blockchains LLC.
[1:42](https://youtu.be/ot_io5Xi13M?t=102)

Trent Van Epps: Protocol testing at WhiteBlock.
[2:05](https://youtu.be/ot_io5Xi13M?t=125)

Bryant Eisenbach: Ethereum community member.
[3:00](https://youtu.be/ot_io5Xi13M?t=180)

Danny Ryan: Research at the Ethereum Foundation. Has also worked on a proposal similar to this [EIP-1011](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1011.md).
[4:40](https://youtu.be/ot_io5Xi13M?t=280)

Danno Ferrin: Works on the Eth1 side of PegaSys at Consensys.
[5:27](https://youtu.be/ot_io5Xi13M?t=327)

????
[5:58](https://youtu.be/ot_io5Xi13M?t=358)

## Discussions
[6:30](https://youtu.be/ot_io5Xi13M?t=390)

Two topics that should be discussed in this call are given:
1. Approach to consensus change on Eth1. [7:10](https://youtu.be/ot_io5Xi13M?t=430)
2. Eth1 token issuance reduction. [7:42](https://youtu.be/ot_io5Xi13M?t=462)

### Double Minting
[8:04](https://youtu.be/ot_io5Xi13M?t=484)

The community is concerned about "minting money in two spots", which ties into the second discussion point. Basically, with both the Eth2 beacon chain and Eth1 POW chain running at the same time, there will be an increased total issuance of ETH. Ideally, the issuance on the Eth1 chain would be reduced using the finality gadget.

### Hardfork Schedule
[9:18](https://youtu.be/ot_io5Xi13M?t=558)
Moving ahead with the finality gadget implies coordinating efforts across eth1 and eth2 chains. The hard fork process in eth1 (and its future) are discussed:
- The hardfork schedule is in flux and there are different release models under consideration. [9:18](https://youtu.be/ot_io5Xi13M?t=558)
- A release timeline that adds small changes to the network more frequently is desirable, as opposed to larger releases with less frequency. [11:44](https://youtu.be/ot_io5Xi13M?t=704)
- [Hardfork vs softfork] Issuance reduction would require a hardfork, however, a finality gadget without an issuance change would not necessarily require a hardfork.  [12:55](https://youtu.be/ot_io5Xi13M?t=775)

### Eth1 Beacon Chain Awareness
[15:20](https://youtu.be/ot_io5Xi13M?t=920)

- At least two ways to do this i.) have operators run a separate Eth2 client alongside their Eth1 client or ii.) embed an Eth2 client inside of Eth1. [16:35](https://youtu.be/ot_io5Xi13M?t=995)
- Having each Eth1 node connect to a separate Eth2 node seems like the most straight forward solution. [18:10](https://youtu.be/ot_io5Xi13M?t=1090)
- Possibility for "herd immunity" where Eth1 nodes that are connected to the beacon chain filter out Eth1 blocks with bad finality information. Involves the scenario where a third-party/miner/etc. is putting finality data inside the eth1 protocol so that nodes not following the beacon chain can still access it. [18:39](https://youtu.be/ot_io5Xi13M?t=1119)
- The Eth2 lightclient protocol is very simple, but it depends on phase 1, so a phase 0 finality gadget would require Eth1 node operators to also run a full beacon node. [20:27](https://youtu.be/ot_io5Xi13M?t=1228)

### Finality Latency
[20:50](https://youtu.be/ot_io5Xi13M?t=1250)

- Initially the follow distance on Eth2 would be 1024 blocks (~4 hours), but would be reduced gradually, potentially down to a few blocks (~1 minute). This does not include epoch finalization, which adds another 12 minutes. [21:30](https://youtu.be/ot_io5Xi13M?t=1290)
- The follow distance would need to be changed gradually, since the Eth1 chain becomes more reliable as the beacon chain acknowledges more blocks, "it's a catch 22". Starting with a short follow distance or dramatically decreasing it could result in Eth2 nodes falling out of sync. [24:45](https://youtu.be/ot_io5Xi13M?t=1485)
- Prototyping and simulating attacks would be valuable. [26:00](https://youtu.be/ot_io5Xi13M?t=1560)
- If the Beacon chain fails, the finality gadget would just stall and the Eth1 chain would keep finalizing on POW. [27:14](https://youtu.be/ot_io5Xi13M?t=1634)

## Closing Thoughts
[27:40](https://youtu.be/ot_io5Xi13M?t=1660)

- Further standardization around Eth1 and Eth2 client interoperability may be useful. [30:40](https://youtu.be/ot_io5Xi13M?t=1840)
- Taking into account attacks against Ethereum Classic may help us understand the risks associated with reducing issuance. [37:30](https://youtu.be/ot_io5Xi13M?t=2250)
