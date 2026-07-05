# Higher Lower — Followers Game

A terminal-based Python game inspired by the "Higher Lower" game format. You're shown two social media accounts (Instagram, celebrities, brands, sports clubs, etc.) with their follower counts in millions — Account A's count is revealed, and you have to guess whether Account B has **higher** or **lower** followers. Guess right and the game continues with a new comparison; guess wrong and your final score is shown.

## How to Play

1. Run the script.
2. Two accounts are shown — Compare A (with follower count) and Compare B (hidden).
3. Type `a` or `b` to guess which one has more followers.
4. If correct, your score goes up and a new round starts with a fresh account to compare.
5. If wrong, the game ends and shows your final score.

## Project Structure

```
higher-lower-followers-game/
├── main.py          # Game loop and core logic
├── game_data.py      # List of accounts (name, description, country, follower_count)
├── art.py            # ASCII art (logo, vs banner)
└── README.md
```

## Requirements

- Python 3.x
- No external libraries needed (only Python's built-in `random` module)

## Running the Game

```bash
python3 main.py
```

## Core Logic

- **`format_data(account)`** — formats an account's name, description, and country into a readable line.
- **`check_answer(guess, a_follower, b_follower)`** — compares follower counts and checks if the user's guess ("a" or "b") matches the account with more followers.
- Each round, the previous Account B becomes the new Account A, and a new random account is picked as the new Account B — keeping the comparisons fresh round after round.
- A duplicate check ensures Account A and Account B are never the same entry in a single round.

## Sample Data Fields

Each account in `game_data.py` is a dictionary with:

| Field | Description |
|---|---|
| `name` | Account/person/brand name |
| `follower_count` | Followers in millions |
| `description` | Short description (role/category) |
| `country` | Country of origin |

## Possible Improvements

- [ ] Add a persistent high score saved to a file
- [ ] Add difficulty levels (e.g., accounts with closer follower counts = harder)
- [ ] Build a GUI or web version (Flask/HTML)
- [ ] Add unit tests for `check_answer()` and duplicate-prevention logic

## Author

Muhammad Taha Ahmad
GitHub: [NinjaVinja](https://github.com/NinjaVinja)
