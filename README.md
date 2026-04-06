WARP Manager v2.3

Универсальный менеджер Cloudflare WARP для **SOCKS5 / custom client**, **TrustTunnel** и **AmneziaWG** с автоопределением и ручным переключением режима.

Возможности

- Автоопределение и ручное переключение режима
- Cloudflare WARP — установка и управление через warp-cli
- SOCKS5-режим — для 3X-UI, TrustTunnel и других совместимых клиентов/сервисов
- Telegram Bot — удалённое управление через Telegram
- Смена IP — автоматическая смена WARP IP
- Мониторинг — системная информация в Telegram
- Настройка порта — гибкая настройка SOCKS5 порта
- Полное удаление — чистка всех следов с сервера

Установка

```bash
curl -fsSL https://raw.githubusercontent.com/h4rd1ns0mn14/WARP-3X/main/install.sh | sudo bash
```

Запуск

```bash
gowarp
```

Режимы работы

| Режим | Описание |
|-------|----------|
| `3xui` | SOCKS5 / Custom Client: WARP через локальный SOCKS5-прокси для 3X-UI, TrustTunnel и других совместимых клиентов |
| `amnezia` | WARP через Docker контейнер AmneziaWG |
| `both` | SOCKS5 / Custom Client + AmneziaWG одновременно |
| `standalone` | Только WARP на сервере |

TrustTunnel

Если `TrustTunnel endpoint` работает на том же сервере, что и `gowarp`, его исходящий трафик можно пустить через локальный WARP SOCKS5.

В `vpn.toml` используйте:

```toml
[forward_protocol.socks5]
address = "127.0.0.1:40000"
extended_auth = false
```

Если в `gowarp` выбран другой порт SOCKS5, подставьте его вместо `40000`.

Структура

```
├── gowarp          # Основной скрипт (bash)
├── install.sh      # Установочный скрипт
└── README.md       # Документация
```

Требования

- Ubuntu / Debian
- Root доступ
- Docker (для AmneziaWG режима)
- 3X-UI, TrustTunnel или другой клиент/сервис с поддержкой SOCKS5 (для режима `3xui`)

Лицензия

MIT
