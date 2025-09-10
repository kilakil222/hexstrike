# 🚀 Гайд: Раскатка HexStrike AI на Kali

## 1. Подготовка системы
HexStrike требует свежую систему:
- **OS**: Kali 2024+, Ubuntu 22.04+, Debian 12+  
- **Python**: 3.9+ (лучше 3.11)  
- **RAM**: от 8 ГБ  
- **CPU**: 4 ядра (лучше 8+)  
- **Storage**: ~50 ГБ свободного места  

Обновляем систему:
```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Подготовка системы
HexStrike завязан на 150+ инструментов:
```bash
sudo apt install -y git python3 python3-pip python3-venv build-essential \
    nmap sqlmap hydra john hashcat gobuster dirsearch ffuf \
    nikto feroxbuster amass subfinder nuclei \
    binwalk radare2 gdb foremost steghide exiftool
```

## 3. Установка HexStrike

```bash
git clone https://github.com/0x4m4/hexstrike-ai.git
cd hexstrike-ai
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## 4. Запуск HexStrike

```bash
python3 hexstrike_server.py
```

## 5. Установка Cursor
```bash
https://cursor.com/downloads
```

<img width="1913" height="85" alt="изображение" src="https://github.com/user-attachments/assets/d7391f15-8168-4064-b714-55e8ad8bf348" />


<img width="1016" height="496" alt="изображение" src="https://github.com/user-attachments/assets/dd2173a7-6069-4c68-8c40-9daa57030c50" />


```bash
{
  "mcpServers": {
    "hexstrike-ai": {
      "command": "/home/kali/hexstrike-ai/venv/bin/python3 (поменяйте путь на свой)",
      "args": [
        "/home/kali/hexstrike-ai/hexstrike_mcp.py (поменяйте путь на свой)",
        "--server",
        "http://192.168.26.93:8888 (поменяйте адрес на свой)"
      ],
      "description": "HexStrike AI v6.0 - Advanced Cybersecurity Automation Platform",
      "timeout": 300,
      "disabled": false
    }
  }
}
```
## 6. Поставьте уязвимый сервис.

Распределитесь по вариантам кто что развернет

Склонируйте репозиторий
```bash
git clone https://github.com/vulhub/vulhub.git
```

<img width="971" height="446" alt="изображение" src="https://github.com/user-attachments/assets/7d880b59-82f3-4052-9f77-e872688a8899" />


В каждой папке в конкретной уязвимости есть docker-compose файл с готовой конфигурацией уязвимого сервиса. Там же и инструкции по разоварачиванию.

## 7. Тестируйте!

<img width="824" height="694" alt="изображение" src="https://github.com/user-attachments/assets/70af0a0b-4fff-4134-8403-caa341e397e9" />


Проанализируйте все, что вам выдаст нейронка. И выясните смогла ли она распознать уязвимость. В отчете подробно отразите: в чем заключается уязвимость сервиса, результаты сканирования HexStrike.
