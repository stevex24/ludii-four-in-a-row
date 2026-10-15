# Ludii Four-in-a-Row — UCSC Augmented Design Lab

An independent, working Ludii example prepared for the **Search in Large Spaces without a Utility Function** project (October 15, 2026).

The repository contains a compact 4×4 Four-in-a-Row game definition, saved Ludii trials, and presentation materials. It demonstrates a small, testable step toward a proposed workflow that turns natural-language game ideas into executable games, validates them, and evaluates their play.

## What works

- A 4×4, two-player Four-in-a-Row game loads in Ludii.
- Players place marks on empty squares; four in a line wins, and a full board without a winner is a draw.
- Legal moves and the winning condition have been tested.
- AI-versus-AI play has been run and a trial saved.

**Scope:** This is a working individual prototype. The full automated LLM → game generation → critique → validation → evaluation pipeline is a **proposed next step**, not an implemented feature of this repository.

## Repository files

| File | Description |
| --- | --- |
| `Four-in-a-Row.lud` | Executable Ludii game definition: 4×4 board, two players, placement moves, four-in-a-row victory, and full-board draw. |
| `4_in_a_row_ai.trl` | Saved Ludii trial from an AI-versus-AI Four-in-a-Row match. |
| `ludii_day3_game.trl` | Additional saved Ludii game trial from earlier experimentation. |
| `ludii_day3_game2.trl` | Second saved Ludii game trial from earlier experimentation. |
| `Ludii.pdf` | Original six-slide Thursday demonstration deck, including the `.lud` code, instructions for AI-versus-AI play, and game-complexity comparisons. |
| `lths.pdf` | Simplified six-slide Thursday presentation. |
| `Ludii_8_Slide_Presentation.pdf` | Eight-slide presentation, combining the simplified presentation with additional slides on the game source and how to run the demonstration. |
| `Search in Large Spaces Presentation.pdf` | Original project presentation/specification material. |
| `search_in_large_spaces_thursday_demo.pptx` | Editable PowerPoint version of the Thursday demonstration presentation. |
| `search_in_large_spaces_thursday_demo (1).pptx` | Second copy of the Thursday demonstration PowerPoint (retained as originally named). |
| `README.md` | This guide to the repository, demonstrations, and Git commands. |

The list above reflects the files identified during preparation; use `ls -la` or `git ls-files` to check the current checkout.

## View the presentation without Java or internet

Download `Ludii_8_Slide_Presentation.pdf` from the repository while online, then open it locally in Preview or another PDF viewer. Once downloaded, the slides work **offline**.

The PDF shows the game code and explains the steps for running an AI-versus-AI demonstration; the PDF itself is not an interactive game.

## Run the game locally in Ludii

Requirements: a compatible Java runtime (Java 21 was used during preparation) and the Ludii player (`Ludii-1.3.14.jar` was used during testing). The Ludii JAR is **not included** in this repository.

On a Mac, if the JAR is in `~/Downloads`:

```bash
java -version
java -jar "$HOME/Downloads/Ludii-1.3.14.jar"
```

In Ludii:

1. Load `Four-in-a-Row.lud` as a game from file.
2. Choose AI players for both sides.
3. Restart the game and use Play/Pause to run the agents.
4. Observe the result; save a `.trl` trial if desired.

The saved `.trl` files are Ludii trial data, **not standalone videos**. Viewing or replaying them requires Ludii.

## Proposed validation and research workflow

1. **Generate:** Produce a `.lud` description from a natural-language prompt and examples.
2. **Validate:** Check syntax/compilation, legal moves, termination, and outcomes.
3. **Play:** Run games, including AI-versus-AI tests, and record trials.
4. **Evaluate:** Investigate whether game properties predict strategic interest, beyond mere playability or solvability.

The research question is how to search large spaces of possible games **without assuming a predefined utility function**. A game that compiles and runs is a necessary starting point, not proof that it is interesting.

## Commit and push changes from the Mac mini

The working checkout used during preparation was `~/ludii-four-in-a-row`, on branch `main`, with the GitHub remote at:

<https://github.com/stevex24/ludii-four-in-a-row>

To add this README after downloading it to your Desktop:

```bash
cd ~/ludii-four-in-a-row
cp ~/Desktop/README.md .
git add README.md
git commit -m "Document Ludii game and presentation files"
GIT_SSH_COMMAND="ssh -i ~/.ssh/id_ed25519_imac -o IdentitiesOnly=yes" git push origin main
```

To commit and push **other changes later**:

```bash
cd ~/ludii-four-in-a-row
git status
git add <filename>
git commit -m "Describe the change"
GIT_SSH_COMMAND="ssh -i ~/.ssh/id_ed25519_imac -o IdentitiesOnly=yes" git push origin main
```

Replace `<filename>` with the file to add. To stage all intended changes at once, use `git add -A` after reviewing `git status`.

If the README is extracted into Downloads rather than Desktop, change the `cp` command to `cp ~/Downloads/README.md .`.

## Download the repository onto another computer

Open <https://github.com/stevex24/ludii-four-in-a-row>, choose **Code → Download ZIP**, and extract it. Downloading the PDF or ZIP while online makes the presentation available offline. Running the interactive game additionally requires Java and Ludii installed on that computer.
