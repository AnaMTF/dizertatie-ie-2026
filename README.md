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
cp .env.example .env
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
cp .env.example .env
python3 main.py
```

The scan flow now uses RabbitMQ in both directions:

1. Backend publishes scan jobs to `scan.jobs.v1` after upload.
2. Python worker consumes jobs, runs TensorFlow/Keras inference, and publishes results to `scan.results.v1`.
3. Backend consumes result events and updates scan status/results.

Before running, ensure model configuration is correct:

- `DEFAULT_MODEL_PATH` in `dizertatie-ie-2026-consumer/.env`
- `MODEL_MAPPING` in `dizertatie-ie-2026-consumer/config.py`
- `MODEL_CLASSES` in `dizertatie-ie-2026-consumer/config.py`
