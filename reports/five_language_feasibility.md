# Five-Language Dataset Feasibility Audit

The Vaani counts below are from the first 1,500 streamed records per language inspected in the existing project audit. They are not total dataset sizes, representative samples, or counts of usable command-word clips. Transcript presence does not prove isolated-command coverage.

| Language   | Vaani audit window                          |   Records with transcript |   Distinct speakers in audit window | MSWC word-level pilot              | Validated command classifier   | Next requirement                                                                           |
|:-----------|:--------------------------------------------|--------------------------:|------------------------------------:|:-----------------------------------|:-------------------------------|:-------------------------------------------------------------------------------------------|
| Kannada    | First 1,500 streamed records; partial audit |                        75 |                                  98 | Not established in current project | Not yet trained/validated      | Identify suitable labelled command words, verify audio, and construct speaker-aware splits |
| Tamil      | First 1,500 streamed records; partial audit |                       109 |                                  10 | Available                          | Tamil 10-class pilot only      | Expand labelled word coverage and reserve an untouched speaker-disjoint evaluation set     |
| Telugu     | First 1,500 streamed records; partial audit |                        22 |                                  13 | Not established in current project | Not yet trained/validated      | Identify suitable labelled command words, verify audio, and construct speaker-aware splits |
| Malayalam  | First 1,500 streamed records; partial audit |                        36 |                                  15 | Not established in current project | Not yet trained/validated      | Identify suitable labelled command words, verify audio, and construct speaker-aware splits |
| Tulu       | First 1,500 streamed records; partial audit |                        68 |                                  67 | Not established in current project | Not yet trained/validated      | Identify suitable labelled command words, verify audio, and construct speaker-aware splits |

## Current conclusion

The project has an implemented Tamil 10-class experimental pilot. A validated five-language keyword-spotting model has not been demonstrated. Kannada, Telugu, Malayalam, and Tulu require suitable labelled command data and separate language-wise evaluation. Tulu data availability is especially unresolved within the current word-level pilot.
