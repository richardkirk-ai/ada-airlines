# ada-airlines — easyJet × Ada CX demo

A five-tab, easyJet-branded sales demo showing Ada's AI agent across every channel.
Self-contained HTML pages sharing one bottom tab-bar (**App · Web · Voice · Channels · MCP**).

| Tab | File | What it is |
|-----|------|-----------|
| **App** | `app.html` | easyJet mobile-app replica; the **Support** tab opens a custom easyJet chat UI wired **live** to the `rkirk-airlines-demo` Ada agent via the headless Frontend Chat API (`embed2.js`). |
| **Web** | `index.html` | Click-through website rebooking flow (ATC-strike cancellation → rebook → EU261 → third-party expenses claim), styled like the real Ada chat widget. |
| **Voice** | `voice.html` | Synced voice-call visual (playbook panel + reaccommodation engine + caption bar + player) of the ATC-strike rebooking call. Built from Ada conversation `6a9aac84c4a1d1d6ec2fbca6`. |
| **Channels** | `channels.html` | One agent across Email, Web, SMS, WhatsApp, Messenger, Instagram, X, Apple Messages, Voice — each an airline scenario; animated email thread. |
| **MCP** | `mcp.html` | How Ada reaches airline systems (Microsoft Dynamics 365, Sabre, Amadeus, TA Connections, Levarti, Refunds/Payments) over MCP to resolve a disruption end-to-end. |

## Notes
- **Live chat (App):** the App's Support chat connects to the real Ada bot. Ada's conversation iframe requires an **https** parent (its `frame-ancestors` allows `https://*`, not `http://localhost`) — so the live chat works when served over https (GitHub Pages / AdaCities), not from a local `http://` server.
- **Voice audio:** no call recording is inlined yet; Voice plays on a virtual clock synced to the transcript. Drop the `.wav` in as a base64 data URI on `<audio id="callAudio">` to enable real audio + waveform (press **S** over the audio to re-sync line times).
- Only external dependency is Google Fonts; everything else is inline. The App additionally loads Ada's `embed2.js`.

Bot: `rkirk-airlines-demo` (Ada) · demo owner: Richard Kirk (Ada SC).
