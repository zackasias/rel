# OrpheusDL - Beatport v2

A Beatport module for the OrpheusDL modular archival music program. This is an updated version that fixes streaming functionality and adds proper download support.

## About OrpheusDL - Beatport

OrpheusDL - Beatport is a module written in Python which allows archiving from Beatport for the modular music archival program. This version implements proper download handling and quality selection.

## Features

- Full download support for all quality tiers
- Proper metadata tagging support
- Web-based authentication flow
- Quality tier support:
  - FLAC (lossless)
  - AAC 256k (high)
  - AAC 128k (medium/low)
- Cover art downloading
- Support for:
  - Single tracks
  - Albums/Releases
  - Playlists (including library playlists)
  - Charts (including genre-based charts)
  - Artists

## Prerequisites

- OrpheusDL base installation
- Python 3.7+
- Required Python packages:
### Core dependencies
requests>=2.31.0  # Needed for create_requests_session
pyyaml>=6.0.1    # Needed for config handling

### Development dependencies
logging>=0.4.9.6  # For debug logging

## Installation

1. Go to your orpheusdl/ directory and run:

```bash
git clone https://github.com/johnneerdael/orpheusdl-beatport-v2.git modules/beatport
```

2. Install required packages:

```bash
pip install -r modules/orpheusdl-beatport-v2/requirements.txt
```

## Usage

Download content using Beatport URLs:

```bash
python orpheus.py https://www.beatport.com/track/example/12345
```

Supported URL types:
- Tracks: `beatport.com/track/...`
- Albums: `beatport.com/release/...`
- Artists: `beatport.com/artist/...`
- Playlists: `beatport.com/playlist/...`
- Library Playlists: `beatport.com/library/playlists/...`
- Charts: `beatport.com/chart/...`
- Genre Charts: `beatport.com/genre/.../hype-...`

## Configuration

### Module Settings
```json
{
    "debug": false,  # Enable for detailed logging
    "username": "",  # Beatport username
    "password": ""   # Beatport password
}
```

### Quality Settings
Quality is determined by Orpheus global settings:
- `lossless` -> FLAC
- `high` -> AAC 256k
- `medium/low` -> AAC 128k

**Note**: Requires an active Beatport "LINK" or "LINK PRO" subscription.

## Technical Details

### Authentication Flow
- Uses web-based authentication
- Handles token refresh automatically
- Validates subscription features

### Download Handling
- Direct download support for all quality tiers
- Proper file extension handling
- Full metadata tagging

### Playlist/Chart Support
- Regular playlists
- User library playlists
- Charts and genre-based charts
- Pagination handling for large collections

## Credits

- Original module by @Dniel97, @glomatico and @reattin used as inspiration, nothing is the same or copied
- Updated implementation by @johnneerdael with the thanks of some friendly helpers
- Based on OrpheusDL framework

## License

This project is licensed under the MIT License - see the LICENSE file for details.
