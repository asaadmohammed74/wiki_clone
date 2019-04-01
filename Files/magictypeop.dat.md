his file was introduced in Conquer Online's “Legends Return” expansion. The file is used in the client for displaying the client's new in-game help windows for profession training and profession skill availability. The file adds in additional options for available skills according to the player's previous professions (metempsychosis). Skills will be added, kept and reset, or removed according to this file. The following file structure was taken from patch 5615. This file is encrypted using the [TQ File Asymmetric Cipher](https://gitlab.com/spirited/conquer/snippets/1840786).

### File Structure

| Position | Description | Example |
| -------- | ----------- | ------- |
| 1 | Index | 1 |
| 2 | Rebirth | 1 |
| 3 | Previous Profession | 15 |
| 4 | Current Profession | 11 |
| 5 | Operation Type | 2 |
| 6-66 | List of skills | 1360,1270,1045,1046,… |

The maximum amount of listed skills per operation is 60.

### Operation Types

| Position | Description |
| -------- | ----------- |
| 0 | Removed after rebirth |
| 2 | Reset after rebirth |
| 4 | Skills learned on first life |
| 5 | Pure skills |
| 6 | Skills that can be learned on second life |
| 7 | Skills learned on second life |