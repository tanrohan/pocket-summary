# Pocket Notes

Rohan Tandon · Interactive iPhone prototype (SwiftUI)

One screen that follows a meeting from "recording ended" to a finished summary:
the recording uploads, the conversation is transcribed line by line, and the
summary is written while you watch.

## Run it

1. Open `Pocket Notes/Pocket Notes.xcodeproj` in Xcode 27 or newer.
2. Choose an iPhone simulator running iOS 27.2 or newer.
3. Press Run (⌘R). The sequence starts on launch and takes about 40 seconds.

No packages, accounts, network, or API keys are needed.

## What to try

- **Watch it generate.** Transcript lines arrive one at a time; a yellow
  highlighter marks the phrases that matter. The lines then fall away until
  only those phrases are left, and the summary is written from them.
- **The ribbon.** The waveform is tinted by who was speaking. Yellow dots mark
  the moments the summary drew on. Once the summary is ready, press and
  drag along it to find a moment; let go to open the transcript there.
- **Trace a key point.** Once the summary is ready, tap any key point to see
  the words it came from. Tap a quote to open that moment in the transcript.
- **Summary / Transcript.** The floating control at the bottom switches between
  the two. The transcript is the full 28-minute conversation, grouped by topic.
- **Jump between chapters.** In Transcript, press and slide along the rounded
  dashes on the right. They grow around your finger while a label previews the
  chapter and time. Release to jump; the green dash follows ordinary scrolling.
- **Replay or skip.** The round button at the top right skips to the finished
  summary while processing, and replays from the start once ready.

## What is real and what is simulated

- The transcript is the Atlas launch review from the original recording kit.
- The summary is written by hand to reflect where the meeting ended (launch
  moved to November 10).
- Upload, transcription, and summary generation are a local timeline. Nothing is
  uploaded and no model is called.
- Light and dark appearance are both supported.

## Project layout

```
Pocket Notes/
  App/        PocketNotesApp.swift   App entry point
  Model/      Meeting.swift          Data types and the sample meeting
              AtlasTranscript.swift  The full transcript, by chapter
              MeetingProcessor.swift The simulated processing timeline
  Views/      MeetingScreen.swift    The single screen and its two panes
              MeetingHeader.swift    Title, date, participants
              SummaryView.swift      Upload, live transcript, written summary
              TranscriptView.swift   Transcript rows and speaker badges
              ChapterIndex.swift     Curved chapter scrubber and preview label
              SourceSheet.swift      The quotes behind a key point
              BottomBar.swift        Glass status pill and tab switch
              Waveform.swift         The recording ribbon
              RevealText.swift       Word-wave reveal and highlighter sweep
  Support/    Theme.swift            Colors, type scale, shared transition
```
