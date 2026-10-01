# Alarm Manager

A simple console-based alarm manager written in Java.

The application allows users to create and manage alarms, check them automatically at the current time, and play an audio notification when an alarm is triggered.

## Features

* Add alarms with a specific time and message
* View all saved alarms
* Sort alarms by time
* Search for an alarm by time
* Edit existing alarms
* Delete alarms
* Automatically check alarms every minute
* Play an audio notification when an alarm is triggered
* Remove triggered alarms automatically

## How It Works

When the application starts, it runs two processes:

* The main thread handles user interaction through the console menu.
* A background executor checks the current time every minute and triggers matching alarms.

Each alarm contains:

* Time in `HH:mm` format
* A custom message

When the current time matches an alarm, the application prints the alarm information and plays the included `alarm.wav` sound.

## Console Menu

```text
1. Add alarm
2. View all alarms
3. Sort alarms by time
4. Find alarm by time
5. Delete alarm
6. Edit alarm
7. Exit
```

## Technologies

* Java
* Java Collections Framework
* `java.time` / `java.text` date and time handling
* `ExecutorService` for background alarm checking
* Java Sound API for audio playback
* IntelliJ IDEA

## Project Structure

```text
Alarm/
├── src/
│   ├── Alarm.java
│   ├── AlarmManager.java
│   └── alarm.wav
├── .gitignore
├── AlarmManager.iml
└── README.md
```

### `Alarm.java`

Represents a single alarm.

Stores:

* alarm time
* alarm message
* audio file used when the alarm is triggered

### `AlarmManager.java`

Contains the main application logic:

* console menu
* alarm creation
* alarm display
* sorting
* searching
* editing
* deleting
* time checking
* sound playback

## Running the Project

1. Clone the repository:

```bash
git clone https://github.com/KatyaYatcenko/Alarm.git
```

2. Open the project in IntelliJ IDEA.

3. Make sure Java is configured.

4. Run `AlarmManager.java`.

5. Use the console menu to create and manage alarms.

## Alarm Format

Alarms use the following time format:

```text
HH:mm
```

Example:

```text
08:30
14:45
21:00
```

When an alarm's time matches the current system time, its message is displayed and the alarm sound is played.

## Notes

* Alarms are stored in memory and are not saved after the application is closed.
* The application checks for alarms once every minute.
* Triggered alarms are automatically removed from the list.
* The included `alarm.wav` file is used as the notification sound.
