# README

## Requirements
- **rclone** – Must be installed and properly configured.  
- **exiftool** – Used to read EXIF metadata (date/time).  
- **bash** – This script is written in Bash.  

## Usage
```bash
./media2cloud [--dry-run] [--keep-source] [--rclone-conf=/path/to/rclone.conf] [--rclone-remote=targetName] [--remote-base-path=/multimedia]
```

```bash
# Example media2cloud.conf

# Name of the remote defined in your rclone configuration (without a colon)
RCLONE_REMOTE="my_remote_name"

# Path to the specific rclone config file
RCLONE_CONF="$HOME/.config/rclone/my_remote_name.conf"

# Base path on the remote where files will be uploaded
REMOTE_BASE_PATH="multimedia"

# Array of local source directories (e.g., memory cards) to scan for media files
# Here we use example UUID names for FAT32 devices
SOURCES=(
  "/run/media/USER/5771-8354"
  "/run/media/USER/4203-ABCD"
)

# Maximum number of parallel jobs for file transfers
# This controls how many files are processed simultaneously.
# Increasing this value can speed up transfers but may increase system load.
MAX_JOBS=4
```
