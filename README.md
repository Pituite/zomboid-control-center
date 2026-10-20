<div align="center">

# 🧟 ZCC

### Run your Project Zomboid servers from your desktop

[![Status: in testing](https://img.shields.io/badge/status-in%20testing-d4a017?style=for-the-badge)](#-where-things-stand)
[![Build 42](https://img.shields.io/badge/Project%20Zomboid-Build%2042-8a9a5b?style=for-the-badge)](https://projectzomboid.com)
[![Windows](https://img.shields.io/badge/desktop-Windows%2010%20%7C%2011-0078D4?style=for-the-badge&logo=windows&logoColor=white)](#-what-you-need)
[![License: GPL v3](https://img.shields.io/badge/license-GPL%20v3-blue?style=for-the-badge)](LICENSE)

You host Project Zomboid for your friends or your community, on a VPS, a rented server or a
machine at home. ZCC lets you do all of it from a Windows app: set the machine up, create the
servers, add mods, change settings, take backups, keep an eye on the players. No terminal, no
config files to edit by hand, no web panel to secure.

[**✨ Features**](#-what-it-does) ·
[**🔧 How it works**](#-how-it-works) ·
[**📋 What you need**](#-what-you-need) ·
[**❓ FAQ**](#-questions)

</div>

---

## 🚦 Where things stand

ZCC is **in testing** and not released yet. A first version for testers is on its way, and this
page will say when you can download it. It supports **Build 42** only.

---

## ✨ What it does

### 🖥️ Your machines
- Add a machine with its address and an SSH access: ZCC installs everything it needs on it
  (Steam's command-line tool, its own small agent, the firewall rules) and checks each step.
- See every machine at a glance: CPU, memory, disk, the servers on it, anything that needs you.
- Several machines, several servers each, all in the same window.

### 🎮 Your servers
- Create a server in a few clicks: name, ports, memory, game branch.
- Start, stop, restart. When players are online, they get a countdown in game first.
- Update the game when Steam has a new build, on your say.
- Schedule restarts and backups. They run on the machine, so your PC can stay off.

### 🧩 Mods and maps
- One mod library per machine, shared by all its servers: a mod is downloaded once.
- Add mods by their Workshop link; ZCC brings their requirements along and puts them in the
  right load order.
- A mod made for another version of the game is refused before it breaks a start.
- ZCC tells you when a mod you use has been updated on the Workshop, and restarts the server
  when it is empty, if you want it to.
- See which maps you load and where they sit on the world.

### ⚙️ Settings
- Every server setting and every game rule (the sandbox), with what it does, checked before it
  is written.
- Changes the game can take live are applied right away; the others wait for the next restart,
  or trigger one with a countdown.

### 💾 Backups
- Scheduled, on demand, and automatically before risky changes.
- Restore in one step. If anything goes wrong, the server is put back as it was.
- Download a backup to your PC, or bring one from another server.

### 👥 Players
- Who is online, who came today and this week, how long they stay.
- Roles, kicks, bans, passwords.
- Where everyone is on the map, and where people spend their time.

### 🎲 Game master
- Give items and vehicles, with pictures taken from your own copy of the game and from the
  server's mods.
- Skills, god mode and the other admin powers, teleports.
- Send the helicopter away, clear the zombies around a player.

### 📜 Logs, console and health
- The server's logs sorted by kind (chat, admin, player actions…) and followed live.
- An RCON console.
- The game's own figures over time: players, lag, memory.

### 📥 Servers you already have
- A server you installed by hand or with LinuxGSM can be **taken over** by ZCC: its world, its
  players and its mods come along.
- And **given back** just as it was, with everything the players did in the meantime.

The app is in **English** and **French**.

---

## 🔧 How it works

```
   ZCC on your Windows PC
        │
        │  SSH, with a key that can only talk to the agent
        ▼
   ZCC agent on each of your machines  ── runs as a normal user, not root
        └── your servers, each in its own folder
```

- 🔒 **Nothing exposed.** There is no web panel and no extra port open to the internet: ZCC
  talks to your machines over SSH, with a key that can do nothing else.
- 🛡️ **No root day to day.** Administrator access is only asked for to install or repair a
  machine, for that one session, and it is never saved.
- 🧠 **The machine has the last word.** Every action is planned and checked by the agent against
  the live state of the server, so a scheduled task, a second PC or a double click can't trip
  over each other.
- 🔄 **It keeps itself up to date.** When a new version of ZCC reaches a machine, its agent updates
  itself, and steps back to the previous version if the new one doesn't start. Your servers keep
  running meanwhile.

---

## 📋 What you need

| | |
|---|---|
| **Your PC** | Windows 10 or 11, 64-bit |
| **Each machine** | Debian 12 or 13, or Ubuntu 24.04 or 26.04, 64-bit |
| **Access** | SSH to the machine, with an account that can use `sudo` for the installation |
| **Memory** | Project Zomboid wants a few gigabytes per server; ZCC tells you how much is left |

---

## ❓ Questions

**Do I need to keep my PC on?**
No. The servers, their restarts and their backups live on the machine. ZCC is only needed when
you want to change something or look at what is going on.

**Can I use it with a server I already have?**
Yes, if it runs on one of the systems above. ZCC can take it over, and give it back later.

**What about Build 41?**
Not for now: ZCC is built and tested for Build 42.

**Does ZCC send anything anywhere?**
No. Once released, it will check for a new version when it starts by downloading one small file
from this page's releases, and that check can be turned off in the settings. Nothing is ever
installed without you saying so.

---

## 📜 License

ZCC is free software under the [GNU General Public License v3](LICENSE).

Project Zomboid is a game by The Indie Stone. ZCC is an independent project, not affiliated with
or endorsed by The Indie Stone.
