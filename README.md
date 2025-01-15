# BirdWeather Report Generator

Generates and emails HTML reports of bird detections from a BirdWeather station using their API. The report includes:
- Species detection counts
- Time-of-day activity patterns
- Station images for each species
- Links to audio recordings of best detections

![birdweather_report](https://github.com/user-attachments/assets/e7ba6433-c9b5-488a-93fe-3798408cc28d)

## Setup

1. Clone this repository
2. Install requirements:
```bash
pip install requests jinja2
```

3. Create a config.py file with your settings:
```python
EMAIL_TO = "your.email@example.com"
EMAIL_FROM = "sender.email@example.com"
EMAIL_PASSWORD = "your_app_password"  # SMTP password (or Gmail app-specific password)
SMTP_SERVER = "smtp.example.com"  # email sending server
SMTP_PORT = 587
STATION_TOKEN = "your_station_token"  # BirdWeather station ID (eg 12345)
```

## Usage

Basic usage with default 24-hour report:
```bash
python birdweather_report.py
```

Generate report for different time period:
```bash
python birdweather_report.py --hours 48  # Last 48 hours
```

## Output

The script generates and emails an HTML report containing:
- Total species count and detection count
- Per-species statistics:
  - Total detections
  - Highest confidence level
  - Hour-by-hour activity heatmap
  - Station photo
  - Link to best detection audio

## Requirements

- Python 3.7+
- requests
- jinja2
- SMTP e-mail credentials
- BirdWeather station ID

## License

MIT License
