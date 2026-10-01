# Label Format and Event Annotation

Each recording session contains a `labelf.label` file providing the final event annotation used for the dataset.

The dataset follows a binary alarm-oriented formulation:

- `Alarm` — intrusion-related event
- absence of an `Alarm` interval — negative / non-intrusive interval

The labels are intended for intrusion-related alarm detection rather than for generic activity recognition or strict room-occupancy classification.

## Positive Intervals

Positive intervals correspond to intrusion-related events, including:

- door entry;
- window entry;
- slow, normal, fast, or stealth-like intrusion;
- single- or multi-person intrusion;
- intrusion accompanied by speech;
- intrusion associated with door-handle, impact, object, or access-related actions.

Boundary interactions are labeled as positive when they occur as part of the intrusion process.

## Negative Intervals

Negative intervals include non-intrusive events and nuisance conditions such as:

- falling or thrown objects;
- door knocking without intrusion;
- environmental or external noise;
- speech without intrusion;
- other non-intrusive disturbances.

These events were intentionally included to provide hard-negative examples that may generate radar or acoustic activity without requiring an alarm.

## Session-Level Interpretation

A session may contain one or more annotated `Alarm` intervals.

Time intervals not marked as `Alarm` are treated as negative.

For fully negative sessions, the `labelf.label` file may contain only the annotation header and no `Alarm` interval. In this case, the complete recording is interpreted as negative.

## Window-Level Labeling

For the reference processing used in the associated study:

- observation window: 1.6 s;
- stride: 0.8 s;
- radar window length: 16 frames at 10 Hz.

Each radar-audio window receives the label corresponding to the event state at the temporal center of the window.

This center-based assignment was used to reduce rapid label transitions near event boundaries while maintaining overlapping windows for temporal alarm evaluation.

## Multimodal Alignment

Radar and audio labels refer to the same event-level ground truth.

Only temporally corresponding radar and audio windows were paired for multimodal evaluation.

The same session-level label definition was used for:

- radar-only evaluation;
- audio-only evaluation;
- early fusion;
- late fusion;
- stateful alarm evaluation;
- cross-environment evaluation in Room 2.

## Room 2

Sessions S071-S080 correspond to the external cross-environment evaluation.

The same event definition and labeling procedure used for Room 1 were retained for Room 2.

Room 2 labels were not used for model training, classifier selection, threshold selection, feature-scaling estimation, fusion-rule selection, or stateful-parameter tuning.
