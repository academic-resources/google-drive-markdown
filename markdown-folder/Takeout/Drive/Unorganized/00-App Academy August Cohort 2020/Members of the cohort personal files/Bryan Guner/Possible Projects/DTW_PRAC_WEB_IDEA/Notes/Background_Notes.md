**Transcription:**

1. A musical signal can be broken into different musical feature representations.
2. To simplify, one can assume there are only four features contained in any signal.
3. The guitar signal will contain dynamic features, that is, the volume of different notes and by extension the relative amplitude of varying sections of the music.
4. It will also contain pitch information, which reveals the frequency or the notes being played at any given time.
5. Further, one may examine the timbre, which relates to the variation from ideal integer multiples of the fundamental frequency that the harmonics of the note occupy, as well as the respective energies contained within each harmonic frequency band.
6. Finally, one may record the tempo or speed that the performance and subsections of it were played at.
7. In terms of dynamics, one may take the mean squared amplitude of segments of a sound file.
8. Alternatively, one may try to remove the issue of variable note amplitude entirely by classifying chords in order to mask out the notes hypothesized to be in a given sound segment by a chord template bit mask.
9. In terms of pitch, there are nearly countless algorithms because this is the most important feature to accurately transcribe music.
10. Almost all of these approaches fall into either time domain analysis (which are usually some variation of autocorrelation) or frequency domain analysis (which is often performed on the results of a FFT (Fast Fourier Transform)).
11. Timbre has analysis techniques similar to Spectral Centroid, however, it does not matter much in the context of transcription because the only information it may extrapolate is what instrument the piece was played on. (fairly irrelevant if instrument is user declared upon login)
12. In terms of tempo, the most promising approach to accurate transcription is the separation of the signal into transient and steady state sections.
13. The transient sections would then signify note onset and therefore yield tempo.
14. Dilation and contraction in the time domain from one performance to the next presents the greatest challenge to accurate mapping of the similarities of two sampled instances of a song’s performance.

**Transcription Indifferent Comparison:**

1. Focusing on a comparison technique allows for much more variance in the timing of the performances of a given song.
1. If transcription-centric comparison was the pillar of such a technology, a comparison technique would still be necessary upon generation of each transcript.
1. Limiting factor now hinges upon the assumption that the tradeoff in foregoing precise transcription is the absence of a sacrifice in choosing less precise transcription techniques that are ostensibly consistently misrepresenting the information in the audio signal in a consistent manner and thus still produce a measure of accuracy rather than precision. This fit’s naturally into the paradigm in which a music student compares against their past progress rather than using other peers to gauge their personal improvement.
