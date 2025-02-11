# 🏠 Docker HA & HA OS

## 🐳 Установка в Docker HA

```bash
sudo docker exec -it homeassistant bash
```
```bash
vi configuration.yaml
```
```yaml
command_line:
  - sensor:
      command: "curl -k --silent 'https://nebo.live/ru/krs/sensors/ulitsa-krasnoi-armii-18' | \
        awk '/<div class=.text.>/ {getline; gsub(/[^0-9]/, \"\", $0); print; exit}'"
      name: "nebo_live_aqi"
      value_template: '{{ value }}'
```
