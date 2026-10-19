# Host Protocol

## Principles

- Messages are short, versioned, bounded, and schema validated.
- Unknown or malformed messages are ignored.
- The host remains fully functional when MAX.sys is absent or crashes.
- A host activity message immediately cancels pending personality events and
  stops MAX.sys-owned audio.

## Proposed host-to-MAX messages

- `host_ready`
- `interaction`
- `critical_activity_started`
- `critical_activity_ended`
- `venue_changed`
- `voice_enabled`
- `shutdown`

## Proposed MAX-to-host events

- `show_prompt`
- `show_message`
- `play_voice_asset`
- `attention_call`
- `dismiss`
- `status`

Each event carries a stable identifier, expiration time, priority, and bounded
payload. The host rejects expired events and retains final authority over
display and playback.
