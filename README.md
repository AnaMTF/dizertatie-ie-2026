# Instructions

Run the commands below to get the project running.

## Cloning the repository

```sh
git clone https://github.com/AnaMTF/dizertatie-ie-2026 --recursive --depth 1
```

## Starting the individual components

### Frontend start:

```sh
cd dizertatie-ie-2026-frontend
npm install
npm run dev
```

### Backend start:

```sh
cd dizertatie-ie-2026-backend
npm install
npm run dev
```

### Message queue start:

```sh
cd dizertatie-ie-2026-rabbitmq
docker compose up -d
/* incomplete */
```

Open web UI using http://localhost:15672

### Tensorflow classification service start:

```sh
cd dizertatie-ie-2026-consumer
python3 -m venv .venv
. .venv/bin/activate
pip3 install -r requirements.txt
python3 main.py
```
