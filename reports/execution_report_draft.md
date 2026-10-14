# Multilingual TinyML Keyword Spotting — Execution Report

## 1. Current scope
The completed experimental implementation is a 10-class Tamil keyword-spotting
pilot using the MLCommons Spoken Words dataset. Five-language data feasibility
was investigated, but a validated five-language command-recognition model
has not been completed.

## 2. Tamil pilot dataset
- Processed clips: 516
- Classes: 10
- Unique speakers: 58
- Audio: mono, 16 kHz, approximately 1 second per clip
- Processed audio paths: all verified to exist
- A speaker-disjoint split was also explored; results must be reported
  separately from the original split because the evaluation protocols differ.

## 3. CNN baseline
- Input: 40-bin log-Mel features, shape 40 x 101 x 1
- Output: 10 classes
- Parameters: 2,274
- Original-split test accuracy: 15%
- Original-split macro-F1: approximately 0.046

## 4. TFLite deployment validation
- Float32 TFLite file: 13,488 bytes
- Dynamic-range TFLite file: 13,488 bytes
- Size reduction from dynamic-range conversion: 0%
- Both TFLite models matched Keras predictions on all 60 original-split
  test examples.
- Test accuracy for both TFLite models: 15%
- Macro-F1 for both: approximately 0.0468
- Float32 mean / p95 inference latency: approximately 0.090 / 0.150 ms
- Dynamic-range mean / p95 inference latency: approximately 0.083 / 0.114 ms

Latency values were measured in Google Colab and are not physical-device
benchmarks. They measure model invocation only, excluding audio acquisition
and feature extraction. The identical file sizes indicate that dynamic-range
conversion did not produce a measurable storage reduction in this model.

## 5. Interpretation and limitations
The conversion and inference-consistency checks succeeded. However, the CNN's
low test accuracy and macro-F1 mean useful keyword recognition has not yet
been demonstrated. Conversion correctness must not be confused with model
quality. Results from the original split must be distinguished from
speaker-disjoint results because the original split contains speaker overlap.

The current deliverable is a Tamil pilot, not a validated five-language
system. Kannada, Telugu, Malayalam, and Tulu still require suitable labelled
command data and evaluation. The available sentence-level data cannot by
itself establish reliable isolated-keyword performance for those languages.

## 6. Next priorities
1. Investigate CNN prediction collapse and class-wise errors.
2. Select a final model using validation data, then evaluate it on an
   untouched test set.
3. Improve and validate recognition before making accuracy claims.
4. If time permits, benchmark on the intended edge device.
5. Build and evaluate the remaining language datasets before claiming
   multilingual coverage.


## 7. Targeted CNN diagnostic and class-weighted experiment

The original CNN predicted only two classes on the original test set,
achieving 15% accuracy and approximately 0.046 macro-F1. A fresh
class-weighted CNN was then trained using the training split, with early
stopping and validation-loss monitoring.

On the 59-example validation split, the class-weighted model achieved
15.25% accuracy and 0.1112 macro-F1. Its predictions covered more classes,
but several classes still had zero predictions. The experiment therefore
did not establish a sufficiently effective CNN classifier.

The saved RBF-SVM achieved 55% accuracy and approximately 0.532 macro-F1
on the original 60-example test split. This is a stronger current baseline,
not a directly comparable guarantee of generalization: the original split
has speaker overlap, and the class-weighted CNN results above are from the
validation split.

## 8. Current conclusion

The pipeline, Tamil pilot processing, model experiments, TFLite conversion,
and conversion-consistency checks have been completed. The best current
direction is to retain the SVM as the leading baseline while treating
unseen-speaker evaluation and further model improvement as unresolved.
The project is not yet a validated five-language keyword-spotting system.


## 9. Leading explored speaker-disjoint baseline

The explored RBF-SVM using static and first-order delta log-Mel features
achieved 46.97% accuracy and 0.4438 macro-F1 on a 66-example
speaker-disjoint test split. This is the leading explored candidate for
unseen-speaker evaluation among the reported experiments.

The test set was used in multiple exploratory comparisons. Consequently,
these metrics are exploratory and should not be presented as an untouched
final benchmark. Further model selection should use training and validation
data, followed by a newly reserved test set if additional data are obtained.

## 10. Five-language scope and evidence

Kannada, Tamil, Telugu, Malayalam, and Tulu remain the intended language
scope. The current trained keyword classifier is a Tamil 10-class pilot.
The project has not yet demonstrated a validated classifier across all five
languages. Language availability in a speech corpus does not establish
adequate coverage of the required isolated command words. Suitable labelled
data, speaker-aware splits, and language-wise evaluation are still required.
