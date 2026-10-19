# MAX.sys

A reusable, bounded personality and event engine for Greg Gorman's interactive
kiosks. MAX.sys supplies timing, attention behavior, discoverable jokes,
validated events, and voice-asset selection without owning the host kiosk's
screen, audio mixer, hardware, or shutdown controls.

Designed and built by Greg Gorman with Max (OpenAI Codex).

## Origin

MAX.sys began inside the
[Raspberry Pi Transporter Console](https://github.com/gwgorman/raspberry-pi-transporter-console)
as a party-safe character who could entertain guests without interfering with
ENERGIZE, self-destruct/abort, GPIO buttons, audio priority, or kiosk recovery.
This project will extract that behavior into a host-neutral library and
sidecar process for Madame Maxime and future installations.

The first planned hosts are the public
[Madame Maxime Fortune-Teller Kiosk](https://github.com/gwgorman/madame-maxime-fortune-teller-kiosk)
and the private Gorman Office Console. Host-specific telemetry, device control,
and household configuration remain in those projects rather than MAX.sys.

## Preserved behavior

- Bounded, schema-validated events
- Interaction-driven personality phases
- Repetition avoidance
- Quiet Watch after prolonged inactivity
- One deliberate attention call after 15 idle minutes, then randomized
  10-20-minute follow-ups
- Crowd-aware scheduling with a one-minute unsolicited-event floor
- Cooldowns for secrets and special responses
- Immediate suspension and dismissal on host-critical activity
- Private voice preference with safe public fallback
- Voice playback disabled until explicitly enabled by the host
- No route to system commands except through a protected host-owned panel

## Boundary

MAX.sys proposes events; the host application decides whether to render or
play them. The host always owns:

- touch and physical input;
- foreground audio priority;
- device control and lighting;
- shutdown, restart, and kiosk exit;
- interruption and emergency behavior; and
- storage policy.

See [Host protocol](docs/HOST_PROTOCOL.md) and
[Migration](docs/MIGRATION.md).

## Public/private asset policy

The public repository may include original fallback copy and freely
redistributable placeholder assets. It must never contain:

- ElevenLabs API keys or other service credentials;
- Greg's private generated voice files;
- private voice IDs when unnecessary for operation;
- event-specific activation schedules; or
- household/network configuration.

Private voice assets remain deployment-local and are selected by stable event
identifier. Missing private assets fall back safely.

## License

MIT. See [LICENSE](LICENSE).
