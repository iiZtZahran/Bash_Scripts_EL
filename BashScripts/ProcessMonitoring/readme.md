# Process Monitor Script

A Bash script for monitoring and managing system processes with interactive features and logging capabilities.

## Features

- **System Process Information**: Display real-time system process information using `top`
- **Process Management**: Kill processes by PID with logging
- **Process Monitoring**: View detailed information about specific processes
- **Real-time Process Tracking**: Monitor specific processes with configurable update intervals
- **Search and Filter**: Filter processes by:
  - CPU usage (sorted)
  - Memory usage (top 10)
  - Username

## Prerequisites

- Bash shell environment
- Standard Unix utilities (`ps`, `top`, `watch`, `kill`)
- Read/write permissions for log file creation

## Configuration

The script uses a configuration file (`config.cfg`) with the following parameters:

```bash
update_interval=2          # Update interval for real-time monitoring (seconds)
cpu_alert_threshold=80     # CPU usage alert threshold (percentage)
mem_alert_threshold=75     # Memory usage alert threshold (percentage)
```

If the configuration file is not found, default values will be used.

## Installation

1. Download the script to your desired location
2. Make it executable:
   ```bash
   chmod +x process_monitor.sh
   ```
3. (Optional) Create a `config.cfg` file in the same directory

## Usage

Run the script:
```bash
./process_monitor.sh
```

### Menu Options

1. **Display System Info**
   - Shows current system processes using `top`

2. **Kill Process**
   - Prompts for a PID
   - Terminates the specified process
   - Logs the action

3. **Search and Filter Processes**
   - Filter options:
     - `cpu`: Sort processes by CPU usage
     - `mem`: Display top 10 processes by memory usage
     - `user`: Show processes for a specific username

4. **Real Time Monitor**
   - Monitors a specific process in real-time
   - Updates based on configured interval
   - Displays: PID, PPID, user, CPU%, memory%, elapsed time, and command

5. **Exit**
   - Exits the script

## Logging

The script maintains a log file (`process_activity.log`) that records:
- Process terminations
- Timestamp for each action

## Example Log Entry
```
2024-10-27 14:30:45 - Process 1234 terminated.
```

