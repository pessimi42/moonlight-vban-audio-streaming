# moonlight-vban-audio-streaming
This repo documents how to succesfully enable microphone thru IP networking

As [Moonlight](https://github.com/moonlight-stream/moonlight-qt/releases/) or [Artemis](https://github.com/wjbeckett/artemis/releases) does not natively support microphone passthru yet and some popular games need co-operation with internal voice chat, we need to make some audio routing to have this happen.

Moonlight has a [fork](https://github.com/logabell/moonlight-qt-mic/releases) that enables microphone passthrough, but the audio quality is poor if it is used over the Internet, might be good enough if gaming pc and Moonlight client are on a same LAN.

This document describes **my solution** to the need to have a clear audio from my **client** to my **gaming rig** which is hundreds of miles away. Eg. [airgpu](https://airgpu.com/), [GameAway](https://www.gameaway.in/), among some independent providers. You can also use Moonlight in your LAN to use gaming rig from different clients.

## Tools needed

[Voicemeeter (Banana)](https://vb-audio.com/Voicemeeter/banana.htm) is a powerful audio mixer that enables a lot of potential for audio-enthusiastics to power up usual PC audio capabilities. Not available for Mac, but quite similar to [Loopback](https://www.rogueamoeba.com/loopback/)

[Tailscale](https://tailscale.com/download), Tailscale is a Zero Trust identity-based connectivity platform that replaces your legacy VPN, SASE, and PAM and connects remote teams, multi-cloud environments, CI/CD pipelines, Edge & IoT devices, and AI workloads. **For this purpose I found that the Tailscale works more flawlessly than traditional VPN solutions**. It is based on the [WireGuard](https://www.wireguard.com/) protocol, but I couldn't get this to work with pure WireGuard peering yet.

# Installing Voicemeeter

First install [Voicemeeter (Banana)](https://vb-audio.com/Voicemeeter/banana.htm) **to both nodes**. Remember to follow the steps, especially the **REBOOTS** before preoceeding.

There are several configuration guides available in YouTube, but I'll explain my way of achieving my goal which may differ from those tutorials.
