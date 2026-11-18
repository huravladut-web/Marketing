# Backend – GalaBizz

Schelet inițial pentru serviciul de backend al proiectului GalaBizz.

## Structură propusă

```
backend/
├── app/
│   ├── __init__.py
│   ├── main.py          # punct de intrare API
│   ├── config.py        # configurare (env vars)
│   ├── models/          # modele de date
│   ├── routes/          # endpoint-uri
│   └── services/        # logică de business
├── requirements.txt
└── README.md
```

## Rulare locală

```bash
cd backend
python -m venv .venv
.venv/Scripts/activate      # Windows
pip install -r requirements.txt
uvicorn app.main:app --reload
```

## Endpoint-uri planificate

| Metodă | Rută | Descriere |
|--------|------|-----------|
| GET | `/health` | health check |
| GET | `/api/events` | listă evenimente gală |
| POST | `/api/events` | creează eveniment |
| GET | `/api/events/{id}` | detalii eveniment |
