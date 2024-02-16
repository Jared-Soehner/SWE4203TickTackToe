# Identified Issues

## Issue #1: Misleading UI Title After Host Starts Game Before Opponent Joins - Perfective

**Description**
Host starts a game without an opponent, receiving a correct "NO_OPPONENT" error. UI displays misleading title "Your Move" for the host (should indicate waiting for opponent).

**Steps to Reproduce:**

1. Open the game as the host.
2. Attempt to start the game without an opponent.
3. Observe the "NO_OPPONENT" error.
4. Verify the UI title incorrectly displays "Your Move".

**Category:**
Perfective

**Priority:**
Medium

This issue falls under Perfective because it:

- Doesn't impact core gameplay functionality (the error message itself works).
- Focuses on improving the user experience (clearer title helps players understand the setup process).
- Doesn't address bugs or critical features, but improves the polish and smoothness of the game.

**Additional Info**
While not game-breaking, the misleading title creates confusion for new players, impacting their understanding of the game's setup process and potentially hindering their overall experience. A clearer message would improve the user experience and onboarding.

<br />

## Issue #2: Reversed Turn Order After Host Attempts Early Move - Corrective

**Description**
A critical issue occurs when the host attempts to make a move before an opponent joins the game. While the system correctly displays a "NO_OPPONENT" error message at this stage, further steps reveal an unexpected behavior. It leads to incorrect turn order. When the opponent subsequently joins the game, the turn order becomes unexpectedly reversed. Despite being the host, the system prevents the host from making their first move, displaying a misleading "NOT_YOUR_TURN" error message. Conversely, the opponent is able to make their move first, disrupting the intended gameplay sequence.

**Steps to Reproduce:**

1. Host opens the game.
2. Attempt to start the game without an opponent.
3. Verify the "NO_OPPONENT" error appears.
4. Crucially: Try to make a move as the host before an opponent joins.
5. Another player joins the game.
6. Observe the host's "NOT_YOUR_TURN" error when trying to play.
7. Observe the opponent can make a move, disrupting the turn order.

**Category:**
Corrective

**Priority:**
High

This issue falls under Corrective because it:

- This issue directly affects the core gameplay mechanic of turn order, which is essential for fair and balanced competitive play. The bug allows the opponent to move first instead of the host, granting them an unfair advantage.
- Fixing this bug is crucial to ensuring correct turn order execution, restoring fairness and integrity to the game.

**Additional Info**
This bug significantly disrupts the core gameplay mechanic of turn order, leading to an unfair advantage for the opponent and affecting the entire game's progression. It requires immediate attention to ensure fair and consistent gameplay for all players.

<br />

## Issue #3: Unrecognized Victory: Missing Winner Announcement After Line Completion - Corrective

**Description**
The host initiates a game, and an opponent joins, allowing the normal progression of gameplay. However, issues arise when a player successfully completes a line, achieving three strikes in a row, column, or diagonal. Surprisingly, the game fails to recognize this as a win. Instead, the UI erroneously displays "No Winner for this Game," despite a player rightfully earning victory. Notably, the game state indicates "gameOver: true," signaling the end of the game, but lacks the necessary announcement of a proper winner. Addressing this discrepancy is crucial to ensure accurate acknowledgment of winning conditions and enhance the overall user experience.

**Steps to Reproduce:**

1. Host launches a game, opponent joins.
2. Host makes the first move by placing X at 0,1.
3. Opponent responds by placing O at 0,0.
4. Host makes their second move by placing X at 1,1.
5. Opponent player Placing O at 1,0.
6. Host Playing X at 2,1 completing a diagonal line (0,1 - 1,1 - 2,1).
7. The game wrongly displays "No Winner for this Game" although X has a winning line.
8. The game state indicates "gameOver: true".

**Category:**
Corrective

**Priority:**
High

This issue falls under Corrective because it:

- The primary objective of Tic Tac Toe is achieving a winning line. Not recognizing a properly formed winning line directly contradicts this objective.
- The "gameOver: true" state correctly signifies the game's end. However, the missing win announcement breaks the expected user experience and gameplay flow.
- Failing to acknowledge a win creates confusion. This negatively impacts the overall user experience.
- This isn't simply a visual inconsistency; it's a functional bug that prevents the game from performing its intended action (announcing the winner).

**Additional Info**
This issue directly impacts the core objective of the game (achieving victory). Failure to recognize a win frustrates players and diminishes the satisfying conclusion of a successful game. Promptly addressing this bug is essential to ensure accurate win detection and enhance overall player satisfaction.

<br />

## Issue 4: Misleading "PLACEMENT_CONFLICT" and "NOT_YOUR_TURN" Errors Triggered by Specific Move Sequence - Corrective

**Description:**

During the course of the game, a critical issue arises when the opponent endeavors to place their mark at a specific location, namely (1,1), under certain conditions. While making this move in isolation is valid, a sequence of actions triggers unexpected errors. In this sequence, the host places "X" at (0,0) and (1,0), and crucially, the opponent places "O" at either (0,1) or (2,1) before attempting to place "O" at (1,1). The problem emerges with an initial "PLACEMENT_CONFLICT" error when trying to place "O" at (1,1), even though the space is technically available. Subsequently, both players encounter "PLACEMENT_CONFLICT" errors for any further attempts on (1,1), and attempting moves elsewhere after the initial error results in a misleading "NOT_YOUR_TURN" message. The expected behavior is for the game to accurately detect the open space at (1,1) and allow the opponent to place their mark following the specified sequence.

**Steps to Reproduce:**

1. Host launches a game, opponent joins.
2. Host takes the first turn anywhere except 1,1. for e.g, (X at 0,0).
3. Opponent takes their turn (O at 0,1) or (0 at 2,1).
4. Host takes another turn anywhere except 1,1. for e.g, (X at 1,0).
5. Observe the following behaviors:
   - Attempting to place O at 1,1 triggers the "PLACEMENT_CONFLICT" error.
   - Placing O elsewhere result in the "NOT_YOUR_TURN" error.

**Category:**
Corrective

**Priority:**
High

This issue falls under Corrective because it:

- The bug directly blocks valid moves at a specific location on the board, hindering game progress and preventing players from making legal moves.
- Instead of accurate information, the "PLACEMENT_CONFLICT" and "NOT_YOUR_TURN" messages are misleading and confusing, frustrating the players and making it difficult to understand the issue.
- It's a bug that impacts the core function of placing marks on the board, which is essential to playing the game.

**Additional Info**
This issue significantly disrupts the game flow and creates confusion for both players. Inaccurate error messages hinder understanding and prevent valid moves, making gameplay frustrating and unreliable. Addressing this bug is crucial to ensure a smooth and enjoyable gaming experience for all players.

<br />

## Issue 5: Tic Tac Toe App Unplayable on Mobile Devices Due to Lack of Optimization - Adaptive

**Description:**

The Tic Tac Toe app currently does not exhibit responsive behavior on mobile devices, leading to suboptimal user experiences. The user interface elements may not adjust appropriately to different screen sizes, causing layout issues, text truncation, or difficulties in interacting with the app on mobile devices.

**Steps to Reproduce:**

1. Open the app on mobile device or emulate in browser using developer tools.
2. Observe layout inconsistencies, text truncation, or other responsiveness issues.
3. Attempt to play the game on mobile, noting any challenges in interaction.

**Category:**
Adaptive

**Priority:**
Medium

This issue falls under Adaptive because it:

- It pertains to the application's ability to adapt and provide a satisfactory user experience across diverse mobile devices.
- Adaptive maintenance aims to address environmental changes, and in this case, the issue involves optimizing the app's layout and interactions for varying mobile screen sizes, aligning with the principles of adaptability and responsiveness.

**Additional Info**
Achieving mobile responsiveness is essential for ensuring a seamless and user-friendly experience across a diverse range of devices. Addressing this adaptive issue will enhance the app's usability and accessibility on mobile platforms.
