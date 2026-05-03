IN GENERAL & NOTES:

Joint project by:
Tomasz Simkiewicz
Jan Wieczorek
Michał Pawlik
Igor Buszta

Live functionality remaind to be implemeted. Project is on hold for now.

DESCRIPTION:

EEG-Powered Chess Interface

The project is a Python-based Brain-Computer Interface that allows users to play chess against the Stockfish engine using only their eye blinks. By analyzing EEG signals, the system translates specific blink patterns into standard Universal Chess Interface moves.

HOW IT WORKS:

The system translates your blinks into UCI strings (e.g., e2e4) using a sequential input method separated by brief pauses.

To input a move, the user blinks to select the starting column, starting row, destination column, and destination row, pausing in between each selection:

    Start File (Letter): Blink 1-8 times (A-H).

    (Pause for > 1.8 seconds)

    Start Rank (Number): Blink 1-8 times (1-8).

    (Pause for > 1.8 seconds)

    End File (Letter): Blink 1-8 times (A-H).

    (Pause for > 1.8 seconds)

    End Rank (Number): Blink 1-8 times (1-8).

The system asks for a final confirmation (a single blink for "Yes") before executing the move on the board and passing the turn to Stockfish.

STRUCTURE:

brain.py:
Test enviroment, pre-recorded .fif files are used. It works.

live.py

This script connects to a live database using the brainaccess_board library. It continually polls the O1 channel, listening for blink events in real-time, and structures the UCI move dynamically as the user inputs their sequence.
