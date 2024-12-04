# ELO Ranking Bot

A Discord bot for managing an ELO-based ranking system for 2v2 games. The bot allows players to join the ranking system, challenge others, report match results, view rankings, and manage ELO decay for inactive players.

## Features

- **Join the Ranking System:** Players can join the leaderboard with a custom name.
- **Challenge Command:** Players can challenge others for a 2v2 match based on their rank proximity.
- **Report Match Results:** Players can report match results, updating the ELO for winners and losers.
- **Rankings Display:** View the current leaderboard sorted by ELO.
- **ELO Decay System:** Automatically reduces the ELO of inactive players daily after a week of inactivity.
- **Activity Check:** Players can check their last active time and how long until decay starts.
- **Admin Commands:** Reset decay periods, remove players, or override ELO values.

## Commands

### Player Commands
| Command              | Description                                                                                         |
|----------------------|-----------------------------------------------------------------------------------------------------|
| `$join`              | Join the ranking system with a custom name.                                                        |
| `$challenge`         | Challenge a partner and two opponents for a 2v2 match.                                             |
| `$results @<winner>` | Report a winner from the match and update ELO for all players.                                       |
| `$leaderboard`       | View the current leaderboard.                                                                      |
| `$cancel`            | Cancel the active match you are in                                                                 |
| `$activity`          | Check your last active time and see how long until ELO decay starts (or if already decaying).      |
| `$report <description>` | Report a bug with description to the admin        |


### Bot Controller Commands
| Command              | Description                                                                                         |
|----------------------|-----------------------------------------------------------------------------------------------------|
| `$override @<user> <new ELO>`  | Override a player's ELO manually.                                                         |
| `$remove @<user>`    | Remove a player from the ranking system.                                                            |
| `$reset_decay`       | Reset the last active time for all players, starting a new decay period.                            |
| `$toggle_decay`      | Toggle the decay function so that decay is not accumulated                                          |
| `$pause`             | Pause challenges so that people can't submit ELO games                                              |
| `$resume`            | Resume challenges so that people can submit ELO games                                               |
| `$early @<user>`     | Adds 15 points to a player's ELO (used for when players are early to practice)                      |

### Admin Commands
| Command              | Description                                                                                         |
|----------------------|-----------------------------------------------------------------------------------------------------|
| `$broadcast <message>`  | Broadcast a message to all the servers the bot is a part of                                      |
| `$servers`             | Show a list of servers the bot is a part of                                                       |
| `$statistics`            | Show a list of statistics for each server the bot is in                                         |

## Bot Setup

***Option 1.*** **Add my bot to your server (Short and Easy)**
``
    - For my visual learner:
        *Video going through the setup process*
            https://youtu.be/LiY_u0w5rWA
```
    1. *Copy and Paste this link into your browser to add the bot to a server:*
    https://discord.com/oauth2/authorize?client_id=1287923287816671293&permissions=275012332624&integration_type=0&scope=bot

    2. *Give permissions to the bot in a specific channel*

    3. *Create and give the 'bot controller' role to users that you want to be able to use the Bot Controller Commands*
```

***Option 2.*** **Create your own environment (Harder)**
```
    1. Download the files in the "One Server" Folder

    2. Update the IDs at the top to the corresponding IDs

    3. Decide where to run the code: either the cloud or a local server

    4. Run it

    - There's a lot more detailed steps I am not going to go through here, if you want to go this route (though not recommended), please message me on instagram @buchanan_roundnet
```



## How ELO Decay Works

- **Activity Tracking:** Each player has a `last_game` timestamp updated whenever they participate in a match.
- **Decay Start:** After 14 days of inactivity, a player's ELO starts decaying.
- **Daily Decay:** ELO decreases daily by a defined factor until the player becomes active again.

## Example Use Cases

1. **Joining the System:**
    - A user types `$join` and provides their custom name.
    - They are added to the ranking system with an initial ELO of 1000.

2. **Challenging Others:**
    - Challenge players with `$challenge`
    - You will be prompted with a series of questions, read and mention specific people for the question.

3. **Reporting Match Results:**
    - After a match, one player types `$results` then mention a user from the winning team.
    - The bot updates the ELO for both teams based on the match outcome.

4. **Checking Activity:**
    - A user types `$activity` to see how many days and hours remain until decay starts.

5. **Role Holder Override:**
    - The admin resets a player’s ELO using `$override`.
    - The admin removes a player using `$remove`.
    - The admin toggles challenges with `$pause` and `$resume`.

## Contributions

Feel free to submit issues or pull requests to improve the bot. All contributions are welcome!

## License

No licenses

## Credits

Developed by John Buchanan (Wolfpack Roundnet).
