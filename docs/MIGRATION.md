# Migration from the Transporter Console

1. Preserve the current `max_personality.py` and its tests in the transporter
   repository until extraction is verified.
2. Move the pure scheduling/state engine first, without audio or UI code.
3. Define and test the versioned host protocol.
4. Move public fallback copy and asset lookup behind stable event IDs.
5. Build a simulator that exercises activity, quiet watch, crowd pulses,
   cooldowns, invalid messages, crashes, and restarts.
6. Integrate one host at a time while retaining its existing local fallback.
7. Remove the embedded copy only after parity and soak tests pass.

The transporter remains the behavior reference during migration; the new
library becomes canonical only after the first host passes the complete test
suite.
