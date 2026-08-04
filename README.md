# ansible-srt-streaming-setup

Minimalny zestaw playbooków Ansible do uruchomienia prostego streamingowego środowiska SRT.

## O projekcie
- Automatyzuje instalację i konfigurację serwerów oraz usług potrzebnych do przesyłania strumieni SRT.
- Zawiera playbooki do instalacji pakietów oraz przygotowania i konfiguracji środowiska.

## Wymagania
- Ansible 2.9+ (zalecane nowsze)
- dostęp SSH do hostów wymienionych w `inventory.ini`

## Szybki start
1. Dostosuj inventory: `inventory.ini`
2. Sprawdź zmienne w [group_vars/all.yaml](group_vars/all.yaml)
3. Uruchom główny playbook:

```bash
ansible-playbook -i inventory.ini playbooks/main.yaml
```

## Minimalne streamowanie SRT
- Ingest (wysyłanie): srt://url:8282/?streamid=live/stream/<nazwa>
- Odbiór (odbieranie): srt://url:8282/live/stream/<nazwa>
- Serwer nasłuchuje na porcie `8282`; klient łączy się do odpowiedniego URI z nazwą strumienia.
 - Statystyki transmisji: http://url:8181/stats
