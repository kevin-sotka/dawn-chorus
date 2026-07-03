# Dawn Chorus

## Brief (from the prompt)
- **Concept:** Echo birdsong phrases by tapping glowing branches; each success adds a bird to a layered chorus while the sun rises. Finish the dawn, hear the symphony you built.
- **Quality bar:** polished
- **Scope:** M
- **Budget:** default (600k)

## Core Concept
It is 5am in a watercolor forest. Five birds perch on five branches that arc across the scene, each with its own color, note, and synthesized voice. One bird sings a short phrase: its branch pulses in sequence with sound and light. You echo the phrase by tapping the branches in order. Get it right and that bird joins a looping ambient chorus, the sky climbs one shade toward gold, and the next bird offers a slightly longer phrase. It is Simon reborn as a sunrise, and the reward for playing well is music.

## Core Loop
Listen to a phrase (2-6 notes, branches light in order) → echo it by tapping branches → success adds the bird's loop to the chorus and advances the sunrise → next bird sings. Mistakes just replay the phrase, softly.

## Win / Lose
Win: all five birds singing together, sun fully risen, full chorus plays over the lit forest with a score card (total retries = star rating: 0 retries 3 stars, 1-3 two stars, 4+ one star). No lose state; dawn always comes. Replay button re-rolls the phrases.

## Objects & Entities
Five branch+bird pairs (wren, robin, blackbird, song thrush, goldfinch: distinct silhouette, accent color, and WebAudio timbre), phrase sequencer, chorus loop engine, sunrise sky (indigo → rose → gold gradient stages), parallax forest silhouette layers, drifting light motes, star-rating end card.

## Mechanics (cause → effect rules)
- Round starts → active bird's phrase plays: each note lights its branch in its color and emits its synth note; other UI dims slightly.
- Player taps a branch → that branch's note + glow always fire (tapping is always musical, never silent).
- Correct next note in phrase → note mote rises into the sky; full phrase correct → bird flutters, sings a flourish, its loop joins the chorus, sky advances one stage.
- Wrong branch → soft muted "brush" sound, phrase gently replays after 600ms; retry counter +1. Never a harsh buzzer.
- Phrase lengths by bird: 2, 3, 4, 5, 6 notes. Phrases are randomized each playthrough from each bird's pentatonic note set (so every dawn sounds different but always consonant).
- All five birds active → 8-bar full chorus finale with the sun cresting the treeline, then star card.

## UI Needs
- [v1] Title overlay (tap to begin, which also unlocks WebAudio), replay-phrase button, retry-count/star display at end, mute toggle, subtle "listen vs your turn" indicator.
- [later] Free-play aviary mode (all branches live, just make music), extra birds, daily seed.

## Chosen Stack + Why
- **Stack:** html (single file, canvas/DOM + WebAudio)
- **Why:** the whole game is timing, gradients, and synthesis; WebAudio oscillators + envelopes make convincing birdsong with zero asset downloads. Single file for GitHub Pages.

## Scope Notes
- **v1 (shippable):** 5 birds, randomized pentatonic phrases, sunrise staging, chorus layering, finale + stars, full audio.
- **Later:** free-play mode, more species, harmony variations by time of day.

## Mobile Considerations
Branches are large tap targets (min 64px) spread across the mid/lower screen in thumb reach; portrait-first layout that also works landscape. Audio starts only after first tap (autoplay policy). No hover anything.

## Polish Hooks (for the Vibe stage)
1. Each correct full phrase: the bird physically sings (beak up, chest puff) while its color floods a wash into the sky.
2. The finale: all five loops align on a downbeat, sun breaks the treeline, motes go golden.
3. Wrong-note grace: the forest never punishes; it leans in and repeats slower, like a patient teacher.
