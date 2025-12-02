<p align="left">
    <!-- Discord Badge -->
    <a href="https://discord.justus0405.com/"><img src="https://img.shields.io/discord/1370519315400495234?logo=Discord&colorA=1e1e2e&colorB=a6e3a1&style=for-the-badge"></a>
    <!-- Version Badge -->
    <a href="https://github.com/Justus0405/Diskcord/blob/main/diskcord"><img src="https://img.shields.io/badge/Version-1.1-blue?colorA=1e1e2e&colorB=cdd6f4&style=for-the-badge"></a>
</p>

<p align="left">
    <!-- Stars Badge -->
	<a href="https://github.com/Justus0405/Diskcord/stargazers"><img src="https://img.shields.io/github/stars/Justus0405/Diskcord?colorA=1e1e2e&colorB=b7bdf8&style=for-the-badge"></a>
    <!-- Issues Badge -->
	<a href="https://github.com/Justus0405/Diskcord/issues"><img src="https://img.shields.io/github/issues/Justus0405/Diskcord?colorA=1e1e2e&colorB=f5a97f&style=for-the-badge"></a>
    <!-- Contributors Badge -->
	<a href="https://github.com/Justus0405/Diskcord/contributors"><img src="https://img.shields.io/github/contributors/Justus0405/Diskcord?colorA=1e1e2e&colorB=a6da95&style=for-the-badge"></a>
</p>

# Diskcord

Diskcord is a lightweight daemon written in bash that monitors the health of your drives and sends periodic updates to a Discord channel via webhook. It checks S.M.A.R.T. data to provide detailed insights about your storage devices, helping you stay ahead of potential failures.

## Features

- Lightweight: The script is written in just a few hundret lines of bash code.
- Background Service: Runs continuously as a daemon to keep your drives under watch.
- S.M.A.R.T Monitoring: Checks various drive statistics.
- Discord Integration: Sends formatted notifications to your Discord webhook.
- Customizable: Select which drives to monitor and how often to check them.

## Notes

The check interval must be formatted as:

- 60s for seconds
- 60m for minutes
- 12h for hours
- 1d for days
- empty, run only once at boot

This allows Diskcord to schedule health checks at the desired frequency.

# Examples

Either run yourself once:

```shell
./diskcord
```

Or run in the background every 1h:

```shell
./diskcord install 1h
```

## Preview

| Passed                                                                                                                              | Failed                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| <img width="350" height="475" alt="passed" src="https://github.com/user-attachments/assets/0bb37e32-b4e5-4732-93fe-0e24b57857e9" /> | <img width="350" height="475" alt="failed" src="https://github.com/user-attachments/assets/d73fa750-39ea-4d6d-8e0c-c3841a37b32f" /> |

## Dependencies

```plaintext
jq
curl
smartmontools
nvme-cli
```

## Installation

1. Clone the repository:

```shell
git clone --depth 1 https://github.com/Justus0405/Diskcord.git
```

2. Navigate to the directory:

```shell
cd Diskcord
```

3. Make the script executable:

```shell
chmod +x diskcord
```

4. Edit the script to configure for which drives to check, webhook url and optionally a user id for pings:

```shell
nano diskcord
```

5. Run the script with the install and either a period argument or without:

```shell
./diskcord install 1d
```

## Usage

```plaintext
usage: diskcord [...]
arguments:
         install 60s, 60m, 12h, or 1d, for seconds, minutes, hours, days.
         uninstall
         60s, 60m, 12h, or 1d, for seconds, minutes, hours, days.
         help
         version
```

#

<p align="center">
	Copyright &copy; 2025-present <a href="https://github.com/Justus0405" target="_blank">Justus0405</a>
</p>

<p align="center">
	<a href="https://github.com/Justus0405/Diskcord/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Justus0405/Diskcord?logo=Github&colorA=1e1e2e&colorB=cba6f7&style=for-the-badge"></a>
</p>
