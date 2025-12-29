
#Структура проекта (файловая и логическая)
projectx/
├── app/
│   ├── Dockerfile
│   ├── manage.py
│   ├── requirements.txt
│   └── projectx/ (settings, wsgi.py, urls.py)
├── nginx/
│   └── nginx.conf
├── docker-compose.yml
├── .env
├── certbot/ (если нужен SSL)
└── deploy/ (k8s manifests / CI scripts)
