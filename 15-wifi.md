# WIFI: let Claude find out why your Wi-Fi is slow (and what to change)

From the reel: *"Claude can now fix your slow Wi-Fi and make it up to 10x faster, for absolutely free."*

**What happened on my laptop (Nov 25, 2026):**
- **16 Wi-Fi networks** around my flat. **10 of them were on channel 6, the same as mine.** Channel 1 had 2 and channel 11 had 3.
- My laptop was linked at **72 Mbps** (2.4 GHz, channel 6, 20 MHz).
- On 5 GHz the same laptop's Wi-Fi chip links at **866 Mbps or more**. That's 12x the link speed.

**Honest part:** the "up to 10x" is the Wi-Fi link between your device and the router. Your internet plan still sets the ceiling, so your real download speed may go up a little or a lot. Yours will vary.

---

## Why a crowded channel slows you down
- On 2.4 GHz, only **channels 1, 6 and 11** don't overlap.
- Networks on the same channel can't talk at once, so they take turns. More neighbors on your channel means more waiting: laggy video calls and slow downloads at busy times.
- **5 GHz** has many more channels and is usually far less crowded. Its range is shorter, so it works best within a room or two of the router.

---

## The prompt (paste into Claude Code)

Open Claude Code in any folder and paste this. It works on Mac and Windows.

```
Help me find out why my Wi-Fi is slow and what to change. Ask before running each command.

1. Detect my OS. Scan the Wi-Fi networks around me:
   - Mac: system_profiler SPAirPortDataType
   - Windows: netsh wlan show networks mode=bssid
   Count how many networks are on each channel, separately for 2.4 GHz and 5 GHz.
   Never print network names or MAC addresses, only channel counts.
2. Tell me which channel and band I'm on now, and my current link speed:
   - Mac: "Transmit Rate" in system_profiler
   - Windows: netsh wlan show interfaces
3. Recommend the best fix in plain words:
   - the emptiest of channels 1, 6 and 11 on 2.4 GHz, or
   - switching to 5 GHz if my router has it.
4. Find my router's settings page from my default gateway:
   - Mac: route -n get default
   - Windows: ipconfig
   Give me the address to open in my browser. If you can tell the brand from the login page, tell me which menu holds the Wi-Fi channel and band settings.
5. Do NOT change anything for me, and never ask for my router password. Just give me the exact steps.
```

**Finding the router login:**
- It's usually on a sticker on the router itself.
- Common addresses are 192.168.0.1 and 192.168.1.1.
- The setting is often under *Wireless / Wi-Fi → Advanced → Channel*. Some ISP routers hide or lock it, so check your provider's app.

---

## Can't touch the router? (shared flat / renting)
Ask Claude to write the message for whoever can. Or use this one:

> Hey! Our Wi-Fi is on channel 6, and 10 neighbor networks are on it too, which is why it's slow at busy times. Could you switch it to channel 1 (or 11), or turn on 5 GHz if the router has it? It takes a minute in the router settings 🙏

---

## When it's NOT the channel
- **Test with a cable**, or right next to the router. If it's still slow, it's your plan or your provider, not the Wi-Fi.
- **Old router:** 802.11n-only routers top out low, and a newer Wi-Fi 6 router helps a lot.
- **Distance and walls:** 5 GHz fades through walls, so a mesh or extender might be the real fix.

Follow [@orzan.ai](https://instagram.com/orzan.ai). The next free one drops tomorrow.
