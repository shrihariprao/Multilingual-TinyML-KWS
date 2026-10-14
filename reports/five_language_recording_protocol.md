# Five-Language TinyML Keyword Spotting
## Recording Protocol — Version 1

### Scope
Languages: Kannada, Tamil, Telugu, Malayalam, Tulu.
Candidate intents: yes, no, start, stop, come, go, help, repeat.

All translations must be reviewed by a competent native speaker
before recording. The candidate list is not yet approved.

### Initial collection target
- 10 distinct speakers per language
- 8 candidate intents per speaker
- 5 repetitions per intent
- 400 planned clips per language
- 2,000 planned clips overall

These are planning targets, not existing recordings or a guarantee
of statistical sufficiency.

### Speaker allocation
- Training: 6 speakers per language
- Validation: 2 different speakers per language
- Test: 2 different speakers per language

Each speaker must belong to exactly one split. A person must not
appear in multiple splits, even under different recording sessions.
Generated speaker IDs in the manifest are placeholders, not real
speaker identities.

### Audio requirements
- Mono WAV, 16,000 Hz
- Aim for approximately 1 second per isolated command
- Record one command per clip, with silence before and after
- Use a quiet room and avoid clipping or heavy background noise
- Preserve the original recording; do not overwrite it during
  preprocessing
- Record the actual language variety or region where the speaker
  is comfortable identifying it

### Session procedure
1. Obtain informed consent before recording.
2. Confirm the native-speaker-reviewed expression and intended
   meaning for each intent.
3. Explain the command naturally; do not coach a specific accent.
4. Randomize the order of commands within each speaker's session.
5. Record five separate repetitions per intent.
6. Re-record only when necessary and document the reason.
7. Check audio integrity, duration, sample rate, clipping and label.
8. Store consent records securely and keep them separate from
   publicly shared audio and research exports.

### Metadata for every clip
language, intent, verified expression, speaker ID, region/dialect
if volunteered, split, repetition, audio path, consent status,
source, quality status and review notes.

### Evaluation safeguards
- Split by speaker before training.
- Fit normalization and learned preprocessing on training data only.
- Use validation data for model selection.
- Keep the test set untouched until final evaluation.
- Report accuracy and macro-F1 for each language and overall.
- Report class-wise errors and model size.
- Distinguish host CPU timing from physical-device latency.

### Current status
No new recordings are confirmed by this document.
Translation review and audio collection remain pending.
Existing Tamil pilot clips are not automatically equivalent to
the eight candidate semantic intents.
